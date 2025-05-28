# Identify-phishing-characteristics-in-a-suspicious-email-sample
# Mail
Return-Path: <phishing@evilhost.ru>
Received: from mail.evilhost.ru (mail.evilhost.ru. [185.200.116.52])
        by mx.google.com with ESMTP id z12si394837qka.56.2025.05.28.12.34.56
        for <target@example.com>;
        Wed, 28 May 2025 12:34:56 -0700 (PDT)
Received-SPF: fail (google.com: domain of phishing@evilhost.ru does not designate 185.200.116.52 as permitted sender) client-ip=185.200.116.52;
Authentication-Results: mx.google.com;
       dkim=fail header.i=@micr0soft-support.com;
       spf=fail (google.com: domain of phishing@evilhost.ru does not designate 185.200.116.52 as permitted sender) smtp.mailfrom=phishing@evilhost.ru;
       dmarc=fail (p=REJECT sp=NONE dis=NONE) header.from=micr0soft-support.com
From: Microsoft Support <security@micr0soft-support.com>
Reply-To: noreply@support-reset-login.com
To: target@example.com
Subject: Urgent: Suspicious Sign-In Attempt Detected!
Date: Wed, 28 May 2025 12:34:53 -0700
Message-ID: <20250528123453.1234567890@micr0soft-support.com>
# return-path is from evilhost. ru, a suspicious Russian-based domain - not from Microsoft
# This shows the sending mail server (185.200.116.52) which is not an official Microsoft mail server.
# we can do an IP WHOIS lookup to check the owner — it would likely show a non-corporate host
# The From looks legit at first glance - but "microsoft" uses a zero instead of an "o" (typosquatting).
# The Reply-To is different again, pointing to another non-Microsoft domain.
# This email fails SPF, DKIM, and DMARC, originates from an untrusted IP, and uses deceptive domains and reply paths.
