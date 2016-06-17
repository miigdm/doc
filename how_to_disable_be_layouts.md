# How to disable BE layouts

In t3kit we have possibility to disable unneeded BE layouts. To do it we just need remove these BE layouts in pageTS.

For example to delete all BE layout add this code in your t3kit installation:

```
backendlayouts.Content >
backendlayouts.ContentMenu >
backendlayouts.ContentMenuSidebar >
backendlayouts.ContentSidebar >
backendlayouts.ContentSidebarMenu >
backendlayouts.Empty >
backendlayouts.GridContainer >
backendlayouts.MenuContent >
backendlayouts.MenuContentSidebar >
backendlayouts.MenuSidebarContent >
backendlayouts.SidebarContent >
backendlayouts.SidebarContentMenu >
backendlayouts.SidebarMenuContent >
backendlayouts.StartPage >
backendlayouts.TopContentContent >
backendlayouts.TopContentContentMenu >
backendlayouts.TopContentContentSidebar >
backendlayouts.TopContentMenuContent >
backendlayouts.TopContentMenuContentSidebar >
backendlayouts.TopContentSidebarContent >
```

BTW this code already added in t3kit, but it commented by default:
`theme_t3kit/Configuration/PageTS/tsconfig.txt`
