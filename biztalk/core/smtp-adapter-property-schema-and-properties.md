---
title: SMTP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UserName property, SMTP adapters
- EmailBodyTextCharset property [SMTP adapters]
- configuring [SMTP adapters], properties
- Subject property [SMTP adapters]
- EmailBodyFileCharset property [SMTP adapters]
- Attachments property [SMTP adapters]
- SMTP adapters, schemas
- EmailBodyText property [SMTP adapters]
- configuring [SMTP adapters], schemas
- CC property [SMTP adapters]
- ReadReceipt property [SMTP adapters]
- Password property [SMTP adapters]
- ReplyBy property [SMTP adapters]
- DeliveryReceipt property [SMTP adapters]
- SMTP adapters, properties
- SMTPAuthenticate property [SMTP adapters]
- EmailBodyFile property [SMTP adapters]
- schemas, SMTP adapters
- SMTPHost property [SMTP adapters]
- From property [SMTP adapters]
- MessagePartsAttachments property [SMTP adapters]
ms.assetid: 6d062fb6-d728-4525-8f0d-bd3f0f8ff7ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcc5e9b1ab3ac9ef5d898c21e0c70638425443a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270988"
---
# <a name="smtp-adapter-property-schema-and-properties"></a><span data-ttu-id="2418b-102">SMTP アダプター プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="2418b-102">SMTP Adapter Property Schema and Properties</span></span>
<span data-ttu-id="2418b-103">次の表は、SMTP アダプター プロパティ スキーマのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2418b-103">The following table lists the properties in the SMTP adapter property schema.</span></span>  
  
 <span data-ttu-id="2418b-104">**名前空間:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span><span class="sxs-lookup"><span data-stu-id="2418b-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties</span></span>  
  
|<span data-ttu-id="2418b-105">名前</span><span class="sxs-lookup"><span data-stu-id="2418b-105">Name</span></span>|<span data-ttu-id="2418b-106">型</span><span class="sxs-lookup"><span data-stu-id="2418b-106">Type</span></span>|<span data-ttu-id="2418b-107">説明</span><span class="sxs-lookup"><span data-stu-id="2418b-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="2418b-108">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="2418b-108">**Username**</span></span>|<span data-ttu-id="2418b-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-109">xs:string</span></span>|<span data-ttu-id="2418b-110">SMTP サーバーでの認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-110">Specify the user name to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="2418b-111">**Password**</span><span class="sxs-lookup"><span data-stu-id="2418b-111">**Password**</span></span>|<span data-ttu-id="2418b-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-112">xs:string</span></span>|<span data-ttu-id="2418b-113">SMTP サーバーでの認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-113">Specify the password to use for authentication with the SMTP server.</span></span>|  
|<span data-ttu-id="2418b-114">**SMTPHost**</span><span class="sxs-lookup"><span data-stu-id="2418b-114">**SMTPHost**</span></span>|<span data-ttu-id="2418b-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-115">xs:string</span></span>|<span data-ttu-id="2418b-116">メッセージの送信時に使用する SMTP サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-116">Specify the name of the SMTP server to use when sending messages.</span></span>|  
|<span data-ttu-id="2418b-117">**From**</span><span class="sxs-lookup"><span data-stu-id="2418b-117">**From**</span></span>|<span data-ttu-id="2418b-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-118">xs:string</span></span>|<span data-ttu-id="2418b-119">SMTP に配置する電子メール アドレスを指定**から**ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2418b-119">Specify the e-mail address to place on the SMTP **From** header.</span></span>|  
|<span data-ttu-id="2418b-120">**Cc**</span><span class="sxs-lookup"><span data-stu-id="2418b-120">**CC**</span></span>|<span data-ttu-id="2418b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-121">xs:string</span></span>|<span data-ttu-id="2418b-122">メッセージのコピーを送信する電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-122">Specify the e-mail address to send a copy of the message.</span></span>|  
|<span data-ttu-id="2418b-123">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="2418b-123">**Subject**</span></span>|<span data-ttu-id="2418b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-124">xs:string</span></span>|<span data-ttu-id="2418b-125">メッセージの件名ヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-125">Specify the subject header for the message.</span></span>|  
|<span data-ttu-id="2418b-126">**SMTPAuthenticate**</span><span class="sxs-lookup"><span data-stu-id="2418b-126">**SMTPAuthenticate**</span></span>|<span data-ttu-id="2418b-127">xs:int</span><span class="sxs-lookup"><span data-stu-id="2418b-127">xs:int</span></span>|<span data-ttu-id="2418b-128">SMTP サーバーで使用する認証の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-128">Specify the type of authentication to use with the SMTP server.</span></span>|  
|<span data-ttu-id="2418b-129">**ReadReceipt**</span><span class="sxs-lookup"><span data-stu-id="2418b-129">**ReadReceipt**</span></span>|<span data-ttu-id="2418b-130">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="2418b-130">xs:boolean</span></span>|<span data-ttu-id="2418b-131">メッセージが読み取られるときに、確認の電子メール メッセージを送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-131">Specify whether to send a confirmation e-mail message when the message is read.</span></span>|  
|<span data-ttu-id="2418b-132">**DeliveryReceipt**</span><span class="sxs-lookup"><span data-stu-id="2418b-132">**DeliveryReceipt**</span></span>|<span data-ttu-id="2418b-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="2418b-133">xs:boolean</span></span>|<span data-ttu-id="2418b-134">メッセージの配信後も、確認の電子メール メッセージを送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-134">Specify whether to send a confirmation e-mail message after delivery of the message.</span></span>|  
|<span data-ttu-id="2418b-135">**EmailBodyText**</span><span class="sxs-lookup"><span data-stu-id="2418b-135">**EmailBodyText**</span></span>|<span data-ttu-id="2418b-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-136">xs:string</span></span>|<span data-ttu-id="2418b-137">送信する電子メールの本文に使用するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-137">Specify text to be used for the body of the e-mail being sent.</span></span>|  
|<span data-ttu-id="2418b-138">**EmailBodyTextCharset**</span><span class="sxs-lookup"><span data-stu-id="2418b-138">**EmailBodyTextCharset**</span></span>|<span data-ttu-id="2418b-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-139">xs:string</span></span>|<span data-ttu-id="2418b-140">ときに送信する電子メールの本文のエンコードを使用する文字セットの指定、 **EmailBodyText**オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="2418b-140">Specify the character set to use for encoding the body of the e-mail being sent when the **EmailBodyText** option is used.</span></span> <span data-ttu-id="2418b-141">SMTP アダプタは、変換、 **EmailBodyText**文字で指定されたセットに**EmailBodyTextCharset**します。</span><span class="sxs-lookup"><span data-stu-id="2418b-141">The SMTP adapter will convert the **EmailBodyText** to the character set specified by **EmailBodyTextCharset**.</span></span>|  
|<span data-ttu-id="2418b-142">**EmailBodyFile**</span><span class="sxs-lookup"><span data-stu-id="2418b-142">**EmailBodyFile**</span></span>|<span data-ttu-id="2418b-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-143">xs:string</span></span>|<span data-ttu-id="2418b-144">ファイルの内容が送信される電子メールやファイルへの完全パスの本文に使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-144">Specifies that the contents of a file will be used for the body of the e-mail being sent and the full path to the file.</span></span> <span data-ttu-id="2418b-145">このパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2418b-145">This path must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="2418b-146">**EmailBodyFileCharset**</span><span class="sxs-lookup"><span data-stu-id="2418b-146">**EmailBodyFileCharset**</span></span>|<span data-ttu-id="2418b-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-147">xs:string</span></span>|<span data-ttu-id="2418b-148">場合に送信する電子メールの本文のエンコードを使用する文字セットの指定、 **EmailBodyFile**プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-148">Specify the character set to use for encoding the body of the e-mail being sent if the **EmailBodyFile** property is set.</span></span> <span data-ttu-id="2418b-149">SMTP アダプターではファイルの変換は行われません。ファイルはこの文字セットであらかじめエンコードされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2418b-149">The SMTP adapter will not perform any conversion on the file; the file must already be encoded in this character set.</span></span> <span data-ttu-id="2418b-150">ファイルにバイト オーダー マーク (BOM) が含まれている場合は、SMTP アダプターで削除されます。</span><span class="sxs-lookup"><span data-stu-id="2418b-150">If the file has a Byte-Order-Mark (BOM), the SMTP adapter will remove it.</span></span>|  
|<span data-ttu-id="2418b-151">**[Attachments]**</span><span class="sxs-lookup"><span data-stu-id="2418b-151">**Attachments**</span></span>|<span data-ttu-id="2418b-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="2418b-152">xs:string</span></span>|<span data-ttu-id="2418b-153">電子メール メッセージにファイルを添付することと、添付するファイルへの完全パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-153">Specifies that a file or files will be attached to the e-mail message and the full path to the file or files.</span></span> <span data-ttu-id="2418b-154">指定されたパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2418b-154">The specified path or paths must be accessible to the host for the SMTP adapter at run time.</span></span>|  
|<span data-ttu-id="2418b-155">**MessagePartsAttachments**</span><span class="sxs-lookup"><span data-stu-id="2418b-155">**MessagePartsAttachments**</span></span>|<span data-ttu-id="2418b-156">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2418b-156">xs:unsignedInt</span></span>|<span data-ttu-id="2418b-157">BizTalk メッセージ部分を電子メール メッセージに添付する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="2418b-157">Specify how BizTalk message parts are attached to the e-mail message.</span></span>|  
|<span data-ttu-id="2418b-158">**ReplyBy**</span><span class="sxs-lookup"><span data-stu-id="2418b-158">**ReplyBy**</span></span>|<span data-ttu-id="2418b-159">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="2418b-159">xs:dateTime</span></span>|<span data-ttu-id="2418b-160">DateTime 値を指定、**返信先**送信する電子メール メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2418b-160">Specify a dateTime value for the **Reply-To** header in the outgoing e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2418b-161">参照</span><span class="sxs-lookup"><span data-stu-id="2418b-161">See Also</span></span>  
 [<span data-ttu-id="2418b-162">SMTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="2418b-162">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)