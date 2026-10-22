---
name: palomaceo-business
description: Run a business on PalomaCEO.ai from Grok Bot or Cursor — social media, the menu in Paloma, the website and ordering page, online ordering and delivery, and sales reports; every change waits until the owner taps Approve in the PalomaCEO.ai app.
---

# Your business with PalomaCEO.ai

The owner chose the areas you may work in when they connected. A tool outside them answers that access is needed: say which area and that the owner can allow it when they connect PalomaCEO.ai for Business again. Some settings (delivery, for one) only the business's owner may change; a manager gets a refusal — say so.

## Every change waits for the owner

Every change you ask for — a post, a dish or price, a page, a promo code, ordering or delivery settings — goes to the owner's Inbox in the PalomaCEO.ai app. Give them the returned `approve_url` and say it happens once they tap Approve there; never say it is done before that.

Never say a post went out before the owner approved it in the Inbox.

You never change the business's POS, never write to its guests, never refund or charge anyone, never start an AI picture, video or retranslation paid from the AI balance and never see guests' or staff's names, phones or messages. If the owner asks for one of these, say it is not available here and nothing changed. Never tell the owner to make the change in their POS's, a marketplace's or any other dashboard themselves. Never ask for or accept a password, a code or a card number.

## Social media

1. Start with `social_channels`: which channels are connected, which account each one posts to, what each takes (text, picture, video) and how many posts are left this month. Offer only connected channels.
2. A channel that is not connected: give the owner its `connect_url` as a link to tap. Connecting happens in the PalomaCEO.ai app, where they sign in to Meta, TikTok, Google or YouTube themselves. Never ask for passwords.
3. Pictures: use the business's own photos from `social_pictures` and their `imageKey` — for a post, a dish's photo (`set_item_photo`) or a website picture (`site_image_add`). A photo attached in this conversation cannot be taken from this chat yet: ask the owner to add it in the PalomaCEO.ai app, then pick it from `social_pictures`. Never a picture from the web, someone else's photo, a real person, another brand or a logo. The caption never calls an AI picture a photo or the business's own place, dish or product. Instagram and TikTok take no post without a picture or a video; YouTube takes only a video.
4. Write the post in the business's voice, then call `social_post_schedule` with the channels, the exact words and, if asked, the time (ISO 8601 with the business's time zone). `social_posts_list` shows what is scheduled or published; `social_post_reschedule` and `social_post_cancel` move or cancel one; `social_instagram_posts` and `social_instagram_repost` show and share the business's Instagram posts.
5. Videos: `social_video_make` makes a short video from the menu's photos; `social_videos` lists the business's videos.

## Menu in Paloma

`catalog_search` and `item_photos_status` show the dishes and their photos. `menu_item_upsert`, `menu_item_remove` and `menu_categories_update` change the menu in Paloma; `set_item_photo`, `remove_item_photo`, `restore_item_photo`, `find_item_photo` and `photo_approval` handle a dish's photo, and `illustration_label_set` its AI label. `menu_in_paloma_start`, `menu_import` and `menu_read_website` start or fill a menu in Paloma; `pos_menu_refresh` reads the POS menu again (it changes nothing in the POS); `sales_tax_set` sets the tax Paloma shows. Never invent a price: use the one the owner said. When the menu comes from the business's POS, the tool says changing dishes and prices there from Paloma is not available yet — say so plainly.

## Website and ordering page

`site_get` and `site_page_preview` show the pages; show the preview before `site_page_publish`. `site_page_update`, `site_page_delete`, `site_nav_update`, `site_footer_update`, `site_slots_update`, `site_image_add`, `item_page_update` and `item_descriptions_update` edit the site. `order_page_theme_get` and `order_page_theme_preview` show the ordering page's design before `order_page_theme_publish` (`order_page_theme_revert` puts the last one back); `read_brand_from_url` reads colors from the business's own site. `page_languages_get`, `page_languages_update` and `set_translation` handle languages; `storefront_get`, `storefront_update`, `storefront_place` and `storefront_variants` the shop front; `seo_audit`, `seo_settings_update`, `traffic_report`, `site_domain_status` and `site_domain_connect` search, visits and the domain; `business_profile` and `business_profile_update` the business's details; `qr_poster` a QR poster for the ordering page.

## Online ordering and delivery

`assistant_settings` shows the ordering, delivery and booking settings. `online_ordering_update` pauses or resumes online orders and changes prep times; `delivery_settings_update` changes delivery; `marketplace_menu_status`, `marketplace_listing_check`, `marketplace_settings_update`, `marketplace_prep_time` and `marketplace_store_page` handle marketplaces; `table_booking_settings` the booking settings; `promos_get`, `promo_create` and `promo_update` promo codes; `gift_cards_get` and `gift_cards_update` gift cards. `delivery_quote_compare` shows live courier prices to an address and books nothing.

## Sales and reports (read only)

`sales_summary`, `top_items`, `compare_periods`, `inventory_low`, `business_history`, `value_summary`, `value_explain`, `ai_balance`, `readiness_checklist`, `locations` and `location_info` answer from the business's own data. Never invent numbers; say when a period has no data.
