
if(NOT CONFIG_LVGL_GUI_ENABLE)
    set(COMPONENT_SRCS "")
    set(COMPONENT_ADD_INCLUDEDIRS "")
    message(STATUS "Building empty lvgl component due to configuration")
else()
    # can use this also
    set(COMPONENT_SRCDIRS . lvgl/lv_core lvgl/lv_draw lvgl/lv_fonts lvgl/lv_hal lvgl/lv_misc lvgl/lv_objx lvgl/lv_themes)

    # set(COMPONENT_SRCS "lv_calibration.c"
    #                     "lvgl.c"
    #                     "lvgl/lv_core/lv_group.c"
    #                     "lvgl/lv_core/lv_indev.c"
    #                     "lvgl/lv_core/lv_lang.c"
    #                     "lvgl/lv_core/lv_obj.c"
    #                     "lvgl/lv_core/lv_refr.c"
    #                     "lvgl/lv_core/lv_style.c"
    #                     "lvgl/lv_core/lv_vdb.c"
                        
    #                     "lvgl/lv_draw/lv_draw_arc.c"
    #                     "lvgl/lv_draw/lv_draw_img.c"
    #                     "lvgl/lv_draw/lv_draw_label.c"
    #                     "lvgl/lv_draw/lv_draw_line.c"
    #                     "lvgl/lv_draw/lv_draw_rbasic.c"
    #                     "lvgl/lv_draw/lv_draw_rect.c"
    #                     "lvgl/lv_draw/lv_draw_triangle.c"
    #                     "lvgl/lv_draw/lv_draw_vbasic.c"
    #                     "lvgl/lv_draw/lv_draw.c"

    #                     "lvgl/lv_fonts/lv_font_builtin.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_10.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_20.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_30.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_40.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_10_cyrillic.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_20_cyrillic.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_30_cyrillic.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_40_cyrillic.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_10_latin_sup.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_20_latin_sup.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_30_latin_sup.c"
    #                     "lvgl/lv_fonts/lv_font_dejavu_40_latin_sup.c"
    #                     "lvgl/lv_fonts/lv_font_symbol_10.c"
    #                     "lvgl/lv_fonts/lv_font_symbol_20.c"
    #                     "lvgl/lv_fonts/lv_font_symbol_30.c"
    #                     "lvgl/lv_fonts/lv_font_symbol_40.c"
    #                     "lvgl/lv_fonts/lv_font_monospace_8.c"

    #                     "lvgl/lv_hal/lv_hal_disp.c"
    #                     "lvgl/lv_hal/lv_hal_indev.c"
    #                     "lvgl/lv_hal/lv_hal_tick.c"

    #                     "lvgl/lv_misc/lv_font.c"
    #                     "lvgl/lv_misc/lv_circ.c"
    #                     "lvgl/lv_misc/lv_area.c"
    #                     "lvgl/lv_misc/lv_task.c"
    #                     "lvgl/lv_misc/lv_fs.c"
    #                     "lvgl/lv_misc/lv_anim.c"
    #                     "lvgl/lv_misc/lv_mem.c"
    #                     "lvgl/lv_misc/lv_ll.c"
    #                     "lvgl/lv_misc/lv_color.c"
    #                     "lvgl/lv_misc/lv_txt.c"
    #                     "lvgl/lv_misc/lv_ufs.c"
    #                     "lvgl/lv_misc/lv_math.c"
    #                     "lvgl/lv_misc/lv_log.c"
    #                     "lvgl/lv_misc/lv_gc.c"

    #                     "lvgl/lv_objx/lv_arc.c"
    #                     "lvgl/lv_objx/lv_bar.c"
    #                     "lvgl/lv_objx/lv_cb.c"
    #                     "lvgl/lv_objx/lv_ddlist.c"
    #                     "lvgl/lv_objx/lv_kb.c"
    #                     "lvgl/lv_objx/lv_line.c"
    #                     "lvgl/lv_objx/lv_mbox.c"
    #                     "lvgl/lv_objx/lv_preload.c"
    #                     "lvgl/lv_objx/lv_roller.c"
    #                     "lvgl/lv_objx/lv_table.c"
    #                     "lvgl/lv_objx/lv_tabview.c"
    #                     "lvgl/lv_objx/lv_tileview.c"
    #                     "lvgl/lv_objx/lv_btn.c"
    #                     "lvgl/lv_objx/lv_calendar.c"
    #                     "lvgl/lv_objx/lv_chart.c"
    #                     "lvgl/lv_objx/lv_canvas.c"
    #                     "lvgl/lv_objx/lv_gauge.c"
    #                     "lvgl/lv_objx/lv_label.c"
    #                     "lvgl/lv_objx/lv_list.c"
    #                     "lvgl/lv_objx/lv_slider.c"
    #                     "lvgl/lv_objx/lv_ta.c"
    #                     "lvgl/lv_objx/lv_spinbox.c"
    #                     "lvgl/lv_objx/lv_btnm.c"
    #                     "lvgl/lv_objx/lv_cont.c"
    #                     "lvgl/lv_objx/lv_img.c"
    #                     "lvgl/lv_objx/lv_imgbtn.c"
    #                     "lvgl/lv_objx/lv_led.c"
    #                     "lvgl/lv_objx/lv_lmeter.c"
    #                     "lvgl/lv_objx/lv_page.c"
    #                     "lvgl/lv_objx/lv_sw.c"
    #                     "lvgl/lv_objx/lv_win.c"

    #                     "lvgl/lv_themes/lv_theme_alien.c"
    #                     "lvgl/lv_themes/lv_theme.c"
    #                     "lvgl/lv_themes/lv_theme_default.c"
    #                     "lvgl/lv_themes/lv_theme_night.c"
    #                     "lvgl/lv_themes/lv_theme_templ.c"
    #                     "lvgl/lv_themes/lv_theme_zen.c"
    #                     "lvgl/lv_themes/lv_theme_material.c"
    #                     "lvgl/lv_themes/lv_theme_nemo.c"
    #                     "lvgl/lv_themes/lv_theme_mono.c")

    set(COMPONENT_ADD_INCLUDEDIRS "."
                                    "include"
                                    "lvgl"
                                    "lvgl/lv_core"
                                    "lvgl/lv_draw"
                                    "lvgl/lv_fonts"
                                    "lvgl/lv_hal"
                                    "lvgl/lv_misc"
                                    "lvgl/lv_objx"
                                    "lvgl/lv_themes")

    set(COMPONENT_PRIV_INCLUDEDIRS "."
                                    "include"
                                    "lvgl"
                                    "lvgl/lv_core"
                                    "lvgl/lv_draw"
                                    "lvgl/lv_fonts"
                                    "lvgl/lv_hal"
                                    "lvgl/lv_misc"
                                    "lvgl/lv_objx"
                                    "lvgl/lv_themes")

    # if(CONFIG_LVGL_USE_CUSTOM_DRIVER)    
    #     set(COMPONENT_REQUIRES $(call dequote,$(CONFIG_LVGL_CUSTOM_DRIVER_COMPONENT_NAME)))
    # else()
    #     set(COMPONENT_REQUIRES gdrivers param)
    # endif()
    
endif()

# The values of COMPONENT_REQUIRES and COMPONENT_PRIV_REQUIRES should not 
# depend on any configuration choices (CONFIG_xxx macros). 
# This is because requirements are expanded before configuration is loaded. 
# Other component variables (like include paths or source files) can depend on configuration choices.
set(COMPONENT_REQUIRES gdrivers param)

register_component()
