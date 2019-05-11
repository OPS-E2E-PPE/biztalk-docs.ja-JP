---
title: POP3 アダプタ プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bfd98117254686f69a590430f46fbd07a4d0b03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394912"
---
# <a name="pop3-adapter-property-schema-and-properties"></a><span data-ttu-id="924d7-102">POP3 アダプタ プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="924d7-102">POP3 Adapter Property Schema and Properties</span></span>
<span data-ttu-id="924d7-103">次の表は、POP3 アダプタ プロパティ スキーマのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="924d7-103">The following table lists the properties in the POP3 adapter property schema.</span></span>  
  
 <span data-ttu-id="924d7-104">**名前空間:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span><span class="sxs-lookup"><span data-stu-id="924d7-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span></span>  
  
|<span data-ttu-id="924d7-105">**名前**</span><span class="sxs-lookup"><span data-stu-id="924d7-105">**Name**</span></span>|<span data-ttu-id="924d7-106">**型**</span><span class="sxs-lookup"><span data-stu-id="924d7-106">**Type**</span></span>|<span data-ttu-id="924d7-107">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="924d7-107">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="924d7-108">**[Subject]**</span><span class="sxs-lookup"><span data-stu-id="924d7-108">**Subject**</span></span>|<span data-ttu-id="924d7-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-109">xs:string</span></span>|<span data-ttu-id="924d7-110">設定するコンテンツを指定します、**サブジェクト**メッセージ ヘッダーには</span><span class="sxs-lookup"><span data-stu-id="924d7-110">Specifies the content placed on the **Subject** header for the message</span></span>|  
|<span data-ttu-id="924d7-111">**From**</span><span class="sxs-lookup"><span data-stu-id="924d7-111">**From**</span></span>|<span data-ttu-id="924d7-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-112">xs:string</span></span>|<span data-ttu-id="924d7-113">設定する電子メール アドレスを指定します、**から**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-113">Specifies the e-mail address placed on the **From** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-114">**変換先**</span><span class="sxs-lookup"><span data-stu-id="924d7-114">**To**</span></span>|<span data-ttu-id="924d7-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-115">xs:string</span></span>|<span data-ttu-id="924d7-116">上に配置された電子メール アドレスを指定します、**に**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-116">Specifies the e-mail address or addresses placed on the **To** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-117">**ReplyTo**</span><span class="sxs-lookup"><span data-stu-id="924d7-117">**ReplyTo**</span></span>|<span data-ttu-id="924d7-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-118">xs:string</span></span>|<span data-ttu-id="924d7-119">設定する電子メール アドレスを指定します、 **ReplyTo**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-119">Specifies the e-mail address placed on the **ReplyTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-120">**Cc**</span><span class="sxs-lookup"><span data-stu-id="924d7-120">**CC**</span></span>|<span data-ttu-id="924d7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-121">xs:string</span></span>|<span data-ttu-id="924d7-122">上に配置された電子メール アドレスを指定します、 **CC**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-122">Specifies the e-mail address or addresses placed on the **CC** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-123">**Date**</span><span class="sxs-lookup"><span data-stu-id="924d7-123">**Date**</span></span>|<span data-ttu-id="924d7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-124">xs:string</span></span>|<span data-ttu-id="924d7-125">設定するコンテンツを指定します、**日付**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-125">Specifies the content placed on the **Date** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-126">**DispositionNotificationTo**</span><span class="sxs-lookup"><span data-stu-id="924d7-126">**DispositionNotificationTo**</span></span>|<span data-ttu-id="924d7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-127">xs:string</span></span>|<span data-ttu-id="924d7-128">設定するコンテンツを指定します、 **DispositionNotificationTo**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="924d7-128">Specifies the content placed on the **DispositionNotificationTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="924d7-129">**ヘッダー**</span><span class="sxs-lookup"><span data-stu-id="924d7-129">**Headers**</span></span>|<span data-ttu-id="924d7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="924d7-130">xs:string</span></span>|<span data-ttu-id="924d7-131">すべての電子メール メッセージのヘッダー フィールドの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="924d7-131">Specifies the content of all of the header fields of the e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="924d7-132">参照</span><span class="sxs-lookup"><span data-stu-id="924d7-132">See Also</span></span>  
 [<span data-ttu-id="924d7-133">POP3 アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="924d7-133">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)