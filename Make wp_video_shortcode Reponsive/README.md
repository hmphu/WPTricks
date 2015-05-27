# Make the WP video shortcode reponsive
    Useful to fix buddypress and rtmedia video size on mobile

- Open functions.php file and add the following code
```php
remove_shortcode( 'video' );
add_shortcode( 'video', apply_filters( 'wp_video_shortcode_handler', 'wp_video_shortcode' ) );
```

- Open style.css and add following css
```css
.mejs-container, .wp-video-shortcode {
    max-width: 100% !important;
}
```

- For rtmedia: open footer.php file and add following css
```html
<style type="text/css"> 
    .rtmedia-activity-container .media-type-video{
        width: 100%;
    }
    .rtmedia-activity-container .mejs-container.mejs-video{
        min-height: 315px;
        min-width: 100%;
    }
    .rtmedia-container ul.rtmedia-list li.rtmedia-list-item div.rtmedia-item-thumbnail {
        width: 100%;
        height: 315px;
        line-height: 315px;
    }
    .rtmedia-container ul.rtmedia-list li.rtmedia-list-item div.rtmedia-item-thumbnail img {
        max-width: 100%;
        max-height: 315px;
    }
    .rtmedia-container .rtmedia-list  .rtmedia-list-item {
        width: 100%;
    }
</style>
```