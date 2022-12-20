# Additional-field-in-wordpress-customize-section
This code will add additional field in wordpress theme customize options and let user edit site easily

#add this code in functions.php file 
You can edit or add extra fields if you want to
Here, I added two sections (one for copyright and another one for social media link)
<code>
	function presswp_theme_customizer($wp_customize) {
		    //adding section in wordpress customizer
		    $wp_customize->add_section('copyright', array(
		        'title'          => 'Copyright Text',
		    ));
		    $wp_customize->add_section('social_media_links', array(
		        'title'          => 'Header Social Media',
		        'priority' 		 => 35,
		    ));
		    $wp_customize->add_section('topbar', array(
		        'title'          => 'Topbar',
		        'priority' 		 => 30,
		    ));
		    //adding setting for copyright text
		    $wp_customize->add_setting('copyright_text', array(
		        'default'        => 'Copyright @2022. All Rights Reserved by Team Omar',
		    ));
		    $wp_customize->add_setting('facebook_link', array(
		        'default'        => 'https://facebook.com/',
		    ));
		    $wp_customize->add_setting('twitter_link', array(
		        'default'        => 'https://twitter.com/',
		    ));
		    $wp_customize->add_setting('linkedin_link', array(
		        'default'        => 'https://linkedin.com/',
		    ));
		    $wp_customize->add_setting('whatsapp_link', array(
		        'default'        => 'https://whatsapp.com/',
		    ));
		    $wp_customize->add_setting('instagram_link', array(
		        'default'        => 'https://instagram.com/',
		    ));
		    $wp_customize->add_setting('presswp_theme_options[topbar_show_hide]', array(
		        'default'        => 'value2',
		        'capability'     => 'edit_theme_options',
		        'type'           => 'option',
		    ));
		    $wp_customize->add_setting('email', array(
		        'default'        => 'example@gmail.com',
		    ));
		    $wp_customize->add_setting('phone', array(
		        'default'        => '',
		    ));
		    // add control
		    $wp_customize->add_control('copyright_text', array(
		        'label'   => 'Copyright text',
		        'section' => 'copyright',
		        'type'    => 'text',
		    ));
		    $wp_customize->add_control('facebook_link', array(
		        'label'   => 'Facebook Link',
		        'section' => 'social_media_links',
		        'type'    => 'text',
		    ));
		    $wp_customize->add_control('twitter_link', array(
		        'label'   => 'Twitter Link',
		        'section' => 'social_media_links',
		        'type'    => 'text',
		    ));
		    $wp_customize->add_control('linkedin_link', array(
		        'label'   => 'Linkedin Link',
		        'section' => 'social_media_links',
		        'type'    => 'text',
		    ));
		    $wp_customize->add_control('whatsapp_link', array(
		        'label'   => 'WhatsApp Link',
		        'section' => 'social_media_links',
		        'type'    => 'text',
		    ));
		    $wp_customize->add_control('instagram_link', array(
		        'label'   => 'Instagram Link',
		        'section' => 'social_media_links',
		        'type'    => 'text',
		    ));

		    // topbar
		    $wp_customize->add_control('email', array(
		        'label'   => 'Email Address',
		        'section' => 'topbar',
		        'type'    => 'email',
		    ));
		    $wp_customize->add_control('phone', array(
		        'label'   => 'Phone Number',
		        'section' => 'topbar',
		        'type'    => 'number',
		    ));
		    $wp_customize->add_setting('tbarshow_hide',
		    array(
		        'sanitize_callback' => 'sanitize_text_field',
		        'default' => 'show'
		    ));
		    $wp_customize->add_control( 'tbarshow_hide', array(
		        'section'               => 'topbar',
		        'label'                 => __( 'Show', 'presswp' ),
		        'type'                  => 'checkbox',
		        'priority'              => 1,
		        'choices'               => array(
		            'show'                  => __('Show', 'presswp'),
		            'hide'                  => __('Hide', 'presswp'),
		        ),theme_
		    ));
		}
		add_action('customize_register', 'presswp_theme_customizer');
</code>

#now its time to display the value in your site
Add below code to the html content

<code>
	
  get_theme_mod('add_control_name_here');
	
</code>

#Let me know it you get your desire output 
