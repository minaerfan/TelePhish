
# TelePhish

TelePhish is a dataset of annotated Telegram messages curated for phishing detection research. This dataset is designed to support phishing detection in Telegram messages by capturing how phishing links are shared and propagated across different Telegram communities. It was developed as part of the following research paper:

> **"Comparing Macro and Micro Approaches for Detecting Phishing Where It Spreads"**  
> Accepted at the **PST 2025 Conference** (International Conference on Privacy, Security & Trust)



## Dataset Overview

Each row in the dataset represents a single Telegram message that contains at least one URL. The dataset includes structural, behavioral, and social context features.


## Column Descriptions

### Identifiers and Group Metadata
| Column | Description |
|--------|-------------|
| `sample_ids` | Row index in the dataset |
| `category` | Group category (`Crypto`, `Games`, or `Darknet`) |
| `group_id` | Unique identifier of the Telegram group |
| `message_id` | Unique message ID within the group |
| `user_id` | Unique sender ID |
| `username` | Sender’s Telegram username (if present) |
| `username_matches_language` | Whether the username matches the group language|

### Features
| Column | Description |
|--------|-------------|
| `message_time`, `date`, `time` | Full timestamp and its components |
| `group_creation_date` | Estimated group creation date |
| `group_age_days_at_message_time` | Age of the group at the message time |
| `days_until_first_post` | Days from group creation to user’s first post |
| `normalized_days_until_first_post` | Normalized version of above |
| `message_content` | Full text content of the message |
| `message_hash` | Hash used for deduplication |
| `message_length` | Number of characters in the message |
| `has_media` | Whether media is attached (image/video/file) |
| `has_text` | Whether message has text content (not just links) |
| `is_reply` | Whether the message is a reply |
| `is_forwarded`, `forwarded_from_id` | Forwarding metadata |
| `url_count` | Number of URLs in the message |
| `urls` | Raw list of URLs |
| `contains_urls` | Boolean indicator (always 1 in this dataset) |
| `message_language`, `group_language` | Detected languages of the message and the group |
| `language_match` | Whether message language matches group language |=
| `formatted_text_count` | Count of bold, italic, emoji, etc. |
| `formatted_text_details` | Formatting details used in the message |
| `reaction_counts` | Number of reactions (if available) |
| `messages_repeat_by_user` | Times the user repeated this exact message |
| `unique_users_per_group_message` | Distinct users who reposted the same message |
| `total_messages` | User’s total messages in the group on that date |=
| `is_malicious` | Whether any URL was flagged as malicious by VirusTotal |
| `is_phishing` | Whether any URL was flagged as phishing by VirusTotal |
| `malicious_link` | URL responsible for phishing label (if any) |
| `raw_message` | Unprocessed raw metadata of the message downloaded directly from Telegram Application |


## Research Context

This dataset was used in our PST 2025 paper to evaluate the effectiveness of different modeling strategies for phishing detection in Telegram.


## Contact Information

For questions, please contact [merfa006@uottawa.ca](mailto:merfa006@uottawa.ca).


