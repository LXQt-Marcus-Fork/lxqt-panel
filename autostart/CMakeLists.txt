file(GLOB DESKTOP_FILES_IN *.desktop.in)

# Translations **********************************
lxqt_translate_desktop(DESKTOP_FILES
    SOURCES
        ${DESKTOP_FILES_IN}
    USE_YAML
)
add_custom_target(lxqt_panel_autostart_desktop_files ALL DEPENDS ${DESKTOP_FILES})
#************************************************

install(FILES
    ${DESKTOP_FILES}
    DESTINATION "${LXQT_ETC_XDG_DIR}/autostart"
    COMPONENT Runtime
)

install(FILES
    lxqt-panel_wayland.desktop
    DESTINATION "/usr/share/applications"
    RENAME "lxqt-panel.desktop"
    COMPONENT Runtime
)
