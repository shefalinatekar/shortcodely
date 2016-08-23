=== Shortcodely ===
Contributors: patilswapnilv, shefalishirodkar20
Plugin Name: shortcodely
Plugin URI: https://github.com/shefalinatekar/rapidfire
Tags: shortcode, widget, page, templates, page template, widget_area, sidebar
Author: patilswapnilv,shefalishirodkar
License: GPLv3 or later
License URI: http://www.gnu.org/licenses/gpl.html
Requires at least: 3.0
Tested up to: 4.1
Stable tag: 1.3.7.1


Shortcodely is a plugin for displaying and managing multiple widgets or a entire widget area (sidebar) into a page using a shortcode.


== Description ==
Insert a widget or multiple widgets or a entire widget area (sidebar) into a page using a shortcode. 

Set up your widget first in a normal sidebar.  Check it works. 
THEN Drag your chosen widgets to the sidebar called "widgets for shortcode".   

Add the do_widget shortcode to the page where you would like the widget to appear (or the do_widget_area)

Using a widget more than once? 

Reference a specific widget instance from the do_widget shortcode, or the chosen sidebar from the do_widget_area shortcode.  Eg: [do_widget id=widget-n]

For example: You could use the query posts widget in the page to create a archive within a page, or the rss widget to list feed content from other sites.  For more details see [anmari.com](http://webdesign.anmari.com/category/plugins/shortcode-any-widget/)

The plugins default action is that it will magically find the settings for your themes sidebar and use the sidebar html to control the widgets output.  In most cases this means the widget will be styled as per the rest of your theme.  If that does not look good, parameters exist to try override this behaviour.  

EG: in twenty-fourteen theme widget text ends up being white on white! widget_classes=none fixes that. Eg: [do_widget widget_classes=none yourwidget]

Changed your theme and worried about losing the sidebar settings ? 

No problem, the plugin will save and restore the widgets_for_shortcode settings.  On display it will then pick up the new themes sidebar settings.  

**Note:**

PLEASE get your widgets working in a sidebar BEFORE activating this plugin, and please read https://wordpress.org/plugins/shortcodely/installation/ and https://wordpress.org/plugins/shortcodely/faq/ and/or see the settings page.  To see a list of your widgets in their sidebars, add ?do_widget_debug to the page with the do_widget shortcode.

== Installation ==

1. Test your chosen widget in a normal sidebar or widget area first. 
2. Then activate this plugin
3. Go to Appearance > widgets and find the " widgets for shortcode" sidebar or widget area
4. Drag your chosen widget from your normal sidebar to the shortcodes sidebar. Save. 
5. Now go to a page and enter a do_widget shortcode The shortcode any widget settings page has some helpful (hopefully) examples and links. 

*  [do_widget widgetname]   eg: [do_widget calendar]
*  [do_widget "widget name"].   eg: [do_widget "tag cloud"]
*  [do_widget id=widgetid] .     eg: [do_widget id=tag-cloud-3]
 
*  [do_widget_area]  (will use the  "widgets in shortcodes" widget area / sidebar
*  [do_widget_area sidebarname] or [do_widget_area widget_area=sidebarname] for another sidebar or widget area - eg: to maximise likelihood of getting your theme's widget css to apply.  

**[do_widget ...] Parameters:**

*  *nameofwidget* or name="*nameofwidget*"  This is NOT the title of the widget.  THis is the name that you see in the widgets menu page even when unassigned to a sidebar.  For existing users , you can also use just the name of the widget without name=.  It must be the first parameter then.  You can only do this with the name, not the id.
*  id=*wordpress assigned id of widget*.   Examples: id=meta-3, id=tag-cloud-9 etc
*  title=false to hide the widgets title OR to override your themes first sidebar html settings for widget titles, use title=*htmltag* where *htmltag* is one of h1,h2,h3,h4,h5,header,strong,em.  
*  wrap=*htmltag* where *htmltag* is one of div,p,main,aside,section.  This will override your themes first sidebar widget wrapping html.
*  widget_classes=none  This will remove the class "widget" from the wrapping html and the class "widget_title" from the title html.  This may be enough to remove any unwanted css caused by your theme. 
*  class=*yourclassname*  By default the plugin will add a class of shortcodely-widget to the wrapping html.  You can use this to add any special css.  Add css either by editing your themes stylesheet if it is a custom theme, or using something like the wordpress custom css plugin.
*  sidebar="*sidebarname*"  will default to widgets_for_shortcode sidebar.  Only use if you want to re-use a widget already being used in another sidebar.  THis is theme dependent and WILL break if you change themes.   Safer to use the widget_id.

**[do_widget_area ...] Parameters:**

*  widget_area=*yourwidgetarea*  defaults to 'widgets_for_shortcodes' if nothing entered
*  widget_area_class=none    /* option to remove theme styling by removing the widget_area class from the sidebar html */
*  widget_classes=none     /* option to remove the widget class from the widget wrappinghtml
*  class=*yourclassname*   default is shortcodely.  This will affect the widget area NOT the individual widgets. At the moment can only remove the widget classes, not replace them when using do_widget_area.
 
Advanced users WARNING: using do_widget_area with a widget area other than the shortcode one means that if you changes themes and the new theme has different sidebars, then this shortcode with a named widget area will not work.  

See the settings page for links to help your create the shortcodes in a page.

The plugin has been tested with most standard widgets (rss feeds, tag cloud, pages, meta, search, and of course my own plugins widgets - upcoming events list, calendar and user lists.

If you use a widget more than once for different reasons, you may need to use the widget id to isolate which widget instance and it's settings to use.  ie: [do_widget id=categories-6] .  If you just use the name, it will display all widgets in the shortcode sidebar with that name (all instances). 


**If you liked this plugin, you might also like my other plugins:**

*  [icalevents.com](http://icalevents.com) - a ics compliant events plugin fully integrated with wordpress, so it will work with many other plugins (seo, maps, social)
*  [wpusersplugin.com](http://wpusersplugin.com) - a suite of plugins to help with membership sites. Major plugin is [shortcodely users](http://wordpress.org/extend/plugins/shortcodely-users/)

== Frequently Asked Questions ==

PLEASE get your widgets working in a sidebar BEFORE activating this plugin, and PLEASE read https://wordpress.org/plugins/shortcodely/installation/ and the settings page before asking any questions.

**Widget help, the widget is doing this, when it should do that** 

Please get the widget working first in a normal sidebar without this plugin and ask for support on the widgets forum it is does not work in a normal sidebar. 

**How to identify widget**

To identify your widget in the shortcode, use the NAME or the ID.  

The name is the generic NAME like "tag cloud".

The id is how wordpress identifies the instance of the widget.  The id is visible at the bottom of the widget settings box.

**Styling, your theme, css, overriding**

Yes anything could happen wrt the appearance.(There are tens of 1000s of themes and widgets.  Multiply out the possible combinations.  Add in css specifity, inheritance and cascading rules.  Consider you are moving the widget out of the sidebar where the the theme and widget plugin expect it to be. )  The effects are very dependent on how your theme has specified the css that may apply to widgets and sidebars/widget areas.  

It may work beautifully and have the content looking like it belongs with your theme.  

This plugin tries to help encourage that 'belonging' look.  If it fails then it offers ways to switch the html and/or the classes being generated.     

 
Examples:
*  you may have undesired effects applying that do not work in the main content area
*  You may have desired effects not applying because the css is specific to a themes sidebar and does not apply to the html in a page.

The plugin can help a bit - Via the plugin you can do the following to affect styling:

*  Remove the general wordpress 'widget' class from the widgets wrapping html and the 'widget_title' from the title html.  ([do_widget *widgetname* widget_classes=none] 

*  Change the 'wrap' html and the title html with parameters wrap=div title=h3. See the settings page.

*  Apply an existing class in your theme.  Use [do_widget *widgetname* class=*yourclass*].

*  Use the additional class 'shortcodely-widget' provided to specify alternate css in your themes stylesheet or with something like wordpress custom css.

One of the new features is as a default setting is that the plugin will try have your current themes first sidebar styling apply to the widgets inserted into a page via the shortcode.

Many folks requested this, insisting that absolutely this is what should be happening and why didn't it? Well..This could be great - Imagine: a plugin that can pick up the theme styling and change it as your theme changes.

The success of this depends very much on how your theme specifies it's css. Does it always use classes ? - more css will apply. Does it lock the css down by sidebar-id: that css will not apply.

It also depends on what the original widget plugin does with css and js. It may have done something thinking that the widget will always be inside a sidebar and not anticipated being in a page. This the shortcde-any-widget plugin has no control over.

For example: An unwanted effect could be white text on a white background as in the twenty fourteen theme.

**If you have an undesired styling effect with the default settings:**

You need to learn the joys of the 'inspect element' tools in various browsers or browser web developer, firebug add-ons, so you can see what css is applying to what html. Then you can either change some of the html or override or change the css.

Options if you don't like the default result:

Use the 'shortcodely-widget' class that has been added to the widget wrapping html to override any css.

eg:
.shortcodely-widget [
color: #000000;
}

Tap into a class you already have in your theme:

[do_widget class=yourclass]

Change the html that the shortcode-any-widget plugin will use.

eg: don't like the h3.widget-title styling ? change the title html to h2 in the shotcode parameters

[do_widget title=h2]

eg: don't like the 'aside' wrapping html styling? change the wrapping html:

[do_widget wrap=div]

If you only using widget, maybe inserting the whole sidebar or widgertarea would give an interesting effect. Sidebar background css may apply.

[do_widget_area]
 

== Screenshots ==

1.  setting up widgets in the widgets for shortcode sidebar. The widget's user interface (UI) is used to provide a UI for the do_widget shortcode.
2.  add shortcode for widgets in a page (must be in the widgets for shortcode sidebar)
3.  widgets in a page 
4.  with the default widget class and with widget_classes=none
    two rss feed widgets in shortcode sidebar - both will show if just name used
5.  The widget id is now visible in the widget window
6.  After clicking on debug message - scroll down till you see the shortcodes sidebar - the widgets and their ids will be listed. Find the id of the widget you want.
7.  Shortcode parameters to remove widget-classes in theme like the twenty-fourteen theme (avoid white text on white background) 
8.  Example of multiple rss widgets in twenty-fourteen theme


 