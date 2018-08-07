From the codex: http://codex.wordpress.org/Template_Tags/the_content#Alternative_Usage

    If you want to achieve the same output that the_content() returns, use the following code:

    <?php
    $content = apply_filters('the_content', $content);
    $content = str_replace(']]>', ']]&gt;', $content);
    ?>

