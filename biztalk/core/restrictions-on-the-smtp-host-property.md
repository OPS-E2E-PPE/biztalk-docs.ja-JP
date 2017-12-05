---
title: "SMTP ホストのプロパティに関する制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 465946f15d11f087995b8000231796c5e204c077
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="restrictions-on-the-smtp-host-property"></a><span data-ttu-id="76983-102">SMTP ホストのプロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="76983-102">Restrictions on the SMTP Host Property</span></span>
<span data-ttu-id="76983-103">SMTP ホストのプロパティは、BizTalk Server からメッセージを送信する際に SMTP アダプタによって使用される SMTP サーバーを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="76983-103">The SMTP host property is a string that specifies the SMTP server that the SMTP adapter will use to send messages from the BizTalk server.</span></span>  
  
 <span data-ttu-id="76983-104">このプロパティには、次の規則および制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="76983-104">The following rules and restrictions apply to this property:</span></span>  
  
-   <span data-ttu-id="76983-105">このプロパティは、アダプタ ハンドラ レベル、エンドポイント レベル、またはその両方の場所で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76983-105">This property must be configured on the adapter handler level, on the endpoint level, or in both places.</span></span>  
  
-   <span data-ttu-id="76983-106">SMTP サーバーのプロパティは、次の文字を含めることはできません: ' ~!</span><span class="sxs-lookup"><span data-stu-id="76983-106">The SMTP server property cannot contain the following characters: \` ~ !</span></span> <span data-ttu-id="76983-107">@ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span><span class="sxs-lookup"><span data-stu-id="76983-107">@ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span></span>  
  
-   <span data-ttu-id="76983-108">SMTP サーバー名は 256 文字以内で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76983-108">The length of the SMTP server name must not exceed 256 characters.</span></span>  
  
 <span data-ttu-id="76983-109">SMTP アダプタでは、上記の規則を使用して、デザイン時に常に SMTP ホスト名を検証します。</span><span class="sxs-lookup"><span data-stu-id="76983-109">The SMTP adapter always validates the SMTP host name at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="76983-110">また、メッセージが SMTP アダプタを使用して動的ポート経由で送信される場合は、実行時に SMTP ホスト名を検証します。</span><span class="sxs-lookup"><span data-stu-id="76983-110">In addition, the SMTP adapter validates the SMTP host name at run time if a message is sent through a dynamic port with the SMTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76983-111">参照</span><span class="sxs-lookup"><span data-stu-id="76983-111">See Also</span></span>  
 [<span data-ttu-id="76983-112">SMTP アダプター構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="76983-112">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)