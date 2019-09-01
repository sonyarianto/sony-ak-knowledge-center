Read this https://askubuntu.com/questions/237564/remap-right-alt-to-behave-as-right-ctrl

On Ubuntu 19.04, To make the mapping system-wide, you should change two files:

```
/usr/share/X11/xkb/symbols/altwin
/usr/share/X11/xkb/symbols/pc
```

Add the following section to the former one:

```
// Ctrl is mapped to the Alt.
partial modifier_keys
xkb_symbols "right_alt" {
    key <LALT> { [ Alt_L, Meta_L ] };
    key <RALT> { type[Group1] = "TWO_LEVEL",
                 symbols[Group1] = [ Control_R, Control_R ] };
    modifier_map Mod1 { Alt_L, Alt_R, Meta_L, Meta_R };
    modifier_map Control { <LCTL>, <RALT> };
};
```

And substitute `include "altwin(meta_alt)"` to the include `"altwin(right_alt)"` in the latter.
