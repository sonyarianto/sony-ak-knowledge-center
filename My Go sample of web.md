package main

import (
    "io"
    "log"
    "net/http"
    "html/template"
)

func hello(w http.ResponseWriter, r *http.Request) {
    io.WriteString(w, "Hello world!")
}

// func about(w http.ResponseWriter, r *http.Request) {
//     //showWwResult, _ := GetWw()
//     //showHoursResult, _ := GetHours()

//     //type Data struct {
//     //    ShowWwResult   []IssueResult
//     //    ShowHoursResult Page
//     //}

//     //data := Data{showWwResult, showHoursResult}

//     data := map[string]interface{}{"OK": "PrasBox", "Nama": "Elan"}

//     //var templates = template.Must(template.ParseFiles("about.html", "templates/ww.html", "templates/hours.html"))
//     var templates = template.Must(template.ParseFiles("about.html"))
//     //templates.ExecuteTemplate(w, "indexPage", data)
//     templates.ExecuteTemplate(w, "about.html", data)
// }

func homePage(w http.ResponseWriter, r *http.Request) {
    var templates = template.Must(template.ParseFiles("index.html"))
    templates.ExecuteTemplate(w, "index.html", nil)
}

func genericPage(w http.ResponseWriter, r *http.Request) {
    var templates = template.Must(template.ParseFiles("generic.html"))
    templates.ExecuteTemplate(w, "generic.html", nil)
}

func elementsPage(w http.ResponseWriter, r *http.Request) {
    var templates = template.Must(template.ParseFiles("elements.html"))
    templates.ExecuteTemplate(w, "elements.html", nil)
}

func queryHandler(w http.ResponseWriter, r *http.Request) {
    keys, ok := r.URL.Query()["key"]
    
    if !ok || len(keys[0]) < 1 {
        log.Println("Url Param 'key' is missing")
        return
    }

    // Query()["key"] will return an array of items, 
    // we only want the single item.
    key := keys[0]

    //log.Println("Url Param 'key' is: " + string(key))
    io.WriteString(w, key)
}

func main() {
    mux := http.NewServeMux()
    mux.Handle("/assets/", http.StripPrefix("/assets/", http.FileServer(http.Dir("assets"))))
    mux.Handle("/images/", http.StripPrefix("/images/", http.FileServer(http.Dir("images"))))

    mux.HandleFunc("/", homePage)
    mux.HandleFunc("/generic", genericPage)
    mux.HandleFunc("/elements", elementsPage)
    mux.HandleFunc("/query", queryHandler)
    //mux.HandleFunc("/about", about)
    http.ListenAndServe(":8888", mux)
}
