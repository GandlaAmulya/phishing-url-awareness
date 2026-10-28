
# Phishing URL Awareness Checker — Test Cases

## Test 1: Normal-looking HTTPS URL
**Input:** `https://www.example.com/login`

**Expected result:** No listed warning signs found. This does NOT prove safety.

## Test 2: IP address with HTTP
**Input:** `http://192.0.2.10/account`

**Expected result:**
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

## Test 3: URL containing @
**Input:** `http://example.com@sample.invalid/login`

**Expected result:**
- Contains an @ symbol; inspect carefully.
- Uses HTTP. HTTPS alone does not prove trust.

## Test 4: Many hostname segments
**Input:** `https://a.b.c.d.e.example.invalid/path`

**Expected result:** Contains many hostname segments/subdomains.

## Test 5: Punycode hostname
**Input:** `https://xn--example.invalid/`

**Expected result:** Contains a punycode-style hostname.
