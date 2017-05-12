# How to disable BE layouts

In t3kit we have possibility to disable unneeded BE layouts. To do it we just need remove these BE layouts in pageTS.

For example to delete all BE layout add this code in your t3kit installation:

```
mod.web_layout.backendlayouts.Content >
mod.web_layout.backendlayouts.ContentMenu >
mod.web_layout.backendlayouts.ContentMenuSidebar >
mod.web_layout.backendlayouts.ContentSidebar >
mod.web_layout.backendlayouts.ContentSidebarMenu >
mod.web_layout.backendlayouts.Empty >
mod.web_layout.backendlayouts.GridContainer >
mod.web_layout.backendlayouts.MenuContent >
mod.web_layout.backendlayouts.MenuContentSidebar >
mod.web_layout.backendlayouts.MenuSidebarContent >
mod.web_layout.backendlayouts.SidebarContent >
mod.web_layout.backendlayouts.SidebarContentMenu >
mod.web_layout.backendlayouts.SidebarMenuContent >
mod.web_layout.backendlayouts.StartPage >
mod.web_layout.backendlayouts.TopContentContent >
mod.web_layout.backendlayouts.TopContentContentMenu >
mod.web_layout.backendlayouts.TopContentContentSidebar >
mod.web_layout.backendlayouts.TopContentMenuContent >
mod.web_layout.backendlayouts.TopContentMenuContentSidebar >
mod.web_layout.backendlayouts.TopContentSidebarContent >
```

BTW this code already added in t3kit, but it commented by default:  
`theme_t3kit/Configuration/PageTS/tsconfig.txt`

