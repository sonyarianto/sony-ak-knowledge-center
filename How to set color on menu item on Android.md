This is the snippets.

```java
MenuItem miSectionCompetition = navigationView.getMenu().findItem(R.id.nav_section_competition);
SpannableString sSectionCompetition = new SpannableString(miSectionCompetition.getTitle());
sSectionCompetition.setSpan(new ForegroundColorSpan(getResources().getColor(R.color.colorSectionTitle)), 0, sSectionCompetition.length(), 0);
miSectionCompetition.setTitle(sSectionCompetition);
```
