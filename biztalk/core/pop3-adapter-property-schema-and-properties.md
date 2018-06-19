---
title: POP3 アダプタ プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: b976aba7161272ebdc65da2b5bcd2067c8cd3a5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264170"
---
# <a name="pop3-adapter-property-schema-and-properties"></a><span data-ttu-id="44370-102">POP3 アダプタ プロパティ スキーマおよびプロパティ</span><span class="sxs-lookup"><span data-stu-id="44370-102">POP3 Adapter Property Schema and Properties</span></span>
<span data-ttu-id="44370-103">POP3 アダプタ プロパティ スキーマのプロパティを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="44370-103">The following table lists the properties in the POP3 adapter property schema.</span></span>  
  
 <span data-ttu-id="44370-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span><span class="sxs-lookup"><span data-stu-id="44370-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties</span></span>  
  
|<span data-ttu-id="44370-105">**名前**</span><span class="sxs-lookup"><span data-stu-id="44370-105">**Name**</span></span>|<span data-ttu-id="44370-106">**型**</span><span class="sxs-lookup"><span data-stu-id="44370-106">**Type**</span></span>|<span data-ttu-id="44370-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="44370-107">**Description**</span></span>|  
|--------------|--------------|---------------------|  
|<span data-ttu-id="44370-108">**Subject**</span><span class="sxs-lookup"><span data-stu-id="44370-108">**Subject**</span></span>|<span data-ttu-id="44370-109">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-109">xs:string</span></span>|<span data-ttu-id="44370-110">設定するコンテンツを指定します、**サブジェクト**メッセージ ヘッダーには</span><span class="sxs-lookup"><span data-stu-id="44370-110">Specifies the content placed on the **Subject** header for the message</span></span>|  
|<span data-ttu-id="44370-111">**From**</span><span class="sxs-lookup"><span data-stu-id="44370-111">**From**</span></span>|<span data-ttu-id="44370-112">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-112">xs:string</span></span>|<span data-ttu-id="44370-113">上に配置する電子メール アドレスを指定します、**から**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-113">Specifies the e-mail address placed on the **From** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-114">**変換先**</span><span class="sxs-lookup"><span data-stu-id="44370-114">**To**</span></span>|<span data-ttu-id="44370-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-115">xs:string</span></span>|<span data-ttu-id="44370-116">電子メール アドレスまたはアドレス上に配置を指定します、**に**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-116">Specifies the e-mail address or addresses placed on the **To** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-117">**ReplyTo**</span><span class="sxs-lookup"><span data-stu-id="44370-117">**ReplyTo**</span></span>|<span data-ttu-id="44370-118">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-118">xs:string</span></span>|<span data-ttu-id="44370-119">上に配置する電子メール アドレスを指定します、 **ReplyTo**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-119">Specifies the e-mail address placed on the **ReplyTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-120">**[CC]**</span><span class="sxs-lookup"><span data-stu-id="44370-120">**CC**</span></span>|<span data-ttu-id="44370-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-121">xs:string</span></span>|<span data-ttu-id="44370-122">電子メール アドレスまたはアドレス上に配置を指定します、 **CC**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-122">Specifies the e-mail address or addresses placed on the **CC** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-123">**[日付]**</span><span class="sxs-lookup"><span data-stu-id="44370-123">**Date**</span></span>|<span data-ttu-id="44370-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-124">xs:string</span></span>|<span data-ttu-id="44370-125">設定するコンテンツを指定します、**日付**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-125">Specifies the content placed on the **Date** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-126">**DispositionNotificationTo**</span><span class="sxs-lookup"><span data-stu-id="44370-126">**DispositionNotificationTo**</span></span>|<span data-ttu-id="44370-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-127">xs:string</span></span>|<span data-ttu-id="44370-128">設定するコンテンツを指定します、 **DispositionNotificationTo**電子メール メッセージのヘッダー フィールド。</span><span class="sxs-lookup"><span data-stu-id="44370-128">Specifies the content placed on the **DispositionNotificationTo** header field of the e-mail message.</span></span>|  
|<span data-ttu-id="44370-129">**ヘッダー**</span><span class="sxs-lookup"><span data-stu-id="44370-129">**Headers**</span></span>|<span data-ttu-id="44370-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="44370-130">xs:string</span></span>|<span data-ttu-id="44370-131">電子メール メッセージのすべてのヘッダー フィールドに設定するコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="44370-131">Specifies the content of all of the header fields of the e-mail message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44370-132">参照</span><span class="sxs-lookup"><span data-stu-id="44370-132">See Also</span></span>  
 [<span data-ttu-id="44370-133">POP3 アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="44370-133">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)