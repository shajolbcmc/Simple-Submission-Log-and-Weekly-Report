=== Simple Submission Log and Weekly Report ===
Contributors: shajol
Tags: submissions, form submissions, contact form, elementor forms, wpforms, contact form 7, fluent forms, csv export, weekly report
Requires at least: 6.2
Tested up to: 6.8
Requires PHP: 7.4
Stable tag: 1.1.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Store website form submissions in WordPress admin, export them to CSV, and send a weekly CSV report by email.

== Description ==

Simple Submission Log and Weekly Report stores form submissions directly inside WordPress so site owners can review leads in the admin area, export them as CSV, and receive a weekly CSV report by email.

It is designed to be simple and lightweight, similar to a submission inbox.

= Features =

* Stores form submissions in the WordPress database.
* Admin page to browse and search submissions.
* View full submitted payload for each entry.
* Export submissions to CSV.
* Send a weekly CSV report by email.
* Works with Contact Form 7, WPForms, Fluent Forms, and Elementor Pro Forms.
* Includes a helper function and action hook for custom forms.
* Integrates with WordPress privacy exporter and eraser tools.

= Supported forms =

* Contact Form 7
* WPForms
* Fluent Forms
* Elementor Pro Forms
* Custom forms via code

= Weekly report =

The plugin schedules a weekly CSV report using WP-Cron. On low-traffic sites, scheduled events may not run exactly on time. For the most reliable delivery, configure a real server cron that triggers WordPress cron regularly.

= Privacy =

This plugin stores submitted form data in your site's WordPress database. Depending on the submitted fields, stored data may include name, email address, phone number, IP address, page URL, and other submitted values.

The plugin also:

* adds suggested privacy policy text in Settings > Privacy
* supports WordPress personal data export for matching email addresses
* supports WordPress personal data erasure for matching email addresses

= Developer usage =

Store a custom submission from your own plugin or theme:

`m4u_submission_logger_store_submission( $array_data, array( 'source' => 'Website Form', 'form_name' => 'Main Form' ) );`

Or fire the action:

`do_action( 'm4u_submission_logger_capture', $array_data, array( 'source' => 'Website Form', 'form_name' => 'Main Form' ) );`

== Installation ==

1. Upload the plugin folder to the `/wp-content/plugins/` directory, or install it through the WordPress plugins screen.
2. Activate the plugin through the 'Plugins' screen in WordPress.
3. Go to **Simple Submission Log** in wp-admin.
4. Open **Settings** to configure weekly report recipients and subject.

== Frequently Asked Questions ==

= Does this plugin send Excel files? =

The plugin sends CSV files. CSV opens in Excel, Google Sheets, and most spreadsheet apps.

= Will this work without Contact Form 7 or Elementor? =

Yes. The plugin works on its own for custom integrations, and automatically captures supported third-party forms when those plugins are active.

= Does this plugin delete data on uninstall? =

Yes. On uninstall it removes its database table and settings. If you want to preserve data, define `M4U_SSLWR_PRESERVE_DATA` as `true` before uninstalling.

== Changelog ==

= 1.1.1 =
* Improved lead field detection for Elementor Pro and multilingual field labels, including Hebrew.



= 1.1.0 =
* Added repository-ready plugin headers and readme.
* Added Elementor Pro Forms support.
* Added privacy policy content, personal data exporter, and eraser integration.
* Improved settings sanitization and CSV generation.
* Added manual "Send Weekly Report Now" action.
* Added uninstall cleanup support.

= 1.0.2 =
* Previous project build.
