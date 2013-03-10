Freelace site parser with email notifier for drupal-power users.

This module can parse some freelance sites for new projects and send emails with
information about it to specific email (http://freelansim.ru for now supported only).
It use simplehtmldom library to parse html content.
This is a blank module to create you own site parser.

EXAMPLE of usage:
  Module haven't any web UI so all changes must be placed in to php code
  in freelance_grabber_freelansimru_grab() function.

  CHANGE $TO FOR YOUR NEEDS.
  This email will be used as email recipient.

  MODIFYING $QUERIES ARRAY WITH YOUR NEEDS.
  You can specify different queries to freelansim.ru site.
  For example, you want to monitor all new projects which contain word 'drupal'.
  So, the original url will be http://freelansim.ru/tasks?q=drupal, or http://freelansim.ru/tasks?q=drupal&page=1 to
  navigate through the pages (page key is required for module).
  In this case, the $query array should be

    $queries = array(
      'drupal' => array(
        'page' => 1,
        'q' => 'drupal'
      )
    );

  Next you need to setup your cron jobs.
  The url to fetch will be: <site_url>/grabber/freelansimru/<type>. <type> must
  equal the $queries item key and in our exapmle it will be 'drupal' (<site_url>/grabber/freelansimru/drupal).
  So use one of unix utilites to fetch <site_url>/grabber/freelansimru/drupal via cron jobs.
  Thats all.

REQUIREMENTS
 - simplehtmldom module.

RECOMMENDATIONS
 - smtp module.

Please notify me if this module was useful for you. <dimasikov at gmail com>