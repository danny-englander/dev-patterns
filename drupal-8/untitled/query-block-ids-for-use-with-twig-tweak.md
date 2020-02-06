# Query block ids for use with twig tweak

In terminal for your project run this command to query block IDs

```bash
grep -r ' id = ' core/modules/*/src/Plugin/Block/;
```

For example, the above will produce:

```bash
/aggregator/src/Plugin/Block//AggregatorFeedBlock.php: *   id = "aggregator_feed_block",
/block_content/src/Plugin/Block//BlockContentBlock.php: *  id = "block_content",
/book/src/Plugin/Block//BookNavigationBlock.php: *   id = "book_navigation",
/forum/src/Plugin/Block//NewTopicsBlock.php: *   id = "forum_new_block",
/forum/src/Plugin/Block//ActiveTopicsBlock.php: *   id = "forum_active_block",
/help/src/Plugin/Block//HelpBlock.php: *   id = "help_block",
/language/src/Plugin/Block//LanguageBlock.php: *   id = "language_block",
/layout_builder/src/Plugin/Block//InlineBlock.php: *  id = "inline_block",
/layout_builder/src/Plugin/Block//FieldBlock.php: *   id = "field_block",
/layout_builder/src/Plugin/Block//ExtraFieldBlock.php: *   id = "extra_field_block",
/node/src/Plugin/Block//SyndicateBlock.php: *   id = "node_syndicate_block",
/search/src/Plugin/Block//SearchBlock.php: *   id = "search_form_block",
/shortcut/src/Plugin/Block//ShortcutsBlock.php: *   id = "shortcuts",
/statistics/src/Plugin/Block//StatisticsPopularBlock.php: *   id = "statistics_popular_block",
/system/src/Plugin/Block//SystemBrandingBlock.php: *   id = "system_branding_block",
/system/src/Plugin/Block//SystemBreadcrumbBlock.php: *   id = "system_breadcrumb_block",
/system/src/Plugin/Block//SystemMainBlock.php: *   id = "system_main_block",
/system/src/Plugin/Block//SystemMenuBlock.php: *   id = "system_menu_block",
/system/src/Plugin/Block//SystemMessagesBlock.php: *   id = "system_messages_block",
/system/src/Plugin/Block//SystemPoweredByBlock.php: *   id = "system_powered_by_block",
/user/src/Plugin/Block//UserLoginBlock.php: *   id = "user_login_block",
/views/src/Plugin/Block//ViewsBlock.php: *   id = "views_block",
/views/src/Plugin/Block//ViewsExposedFilterBlock.php: *   id = "views_exposed_filter_block",
/workspaces/src/Plugin/Block//WorkspaceSwitcherBlock.php: *   id = "workspace_switcher",

```



