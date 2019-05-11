---
title: SMTP ホストのプロパティに関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60eee7ce4acb940d2d0011ead80bdcf9c5ed335c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254885"
---
# <a name="restrictions-on-the-smtp-host-property"></a><span data-ttu-id="cb418-102">SMTP ホストのプロパティに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="cb418-102">Restrictions on the SMTP Host Property</span></span>
<span data-ttu-id="cb418-103">SMTP ホストのプロパティは、BizTalk server からメッセージを送信する SMTP アダプタを使用する SMTP サーバーを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="cb418-103">The SMTP host property is a string that specifies the SMTP server that the SMTP adapter will use to send messages from the BizTalk server.</span></span>  
  
 <span data-ttu-id="cb418-104">このプロパティには、次の規則と制限事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb418-104">The following rules and restrictions apply to this property:</span></span>  
  
- <span data-ttu-id="cb418-105">このプロパティは、エンドポイント レベルで、または両方の場所のアダプタ ハンドラ レベルで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb418-105">This property must be configured on the adapter handler level, on the endpoint level, or in both places.</span></span>  
  
- <span data-ttu-id="cb418-106">SMTP サーバーのプロパティは、次の文字を含めることはできません ' ~!。</span><span class="sxs-lookup"><span data-stu-id="cb418-106">The SMTP server property cannot contain the following characters: \` ~ !</span></span> <span data-ttu-id="cb418-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span><span class="sxs-lookup"><span data-stu-id="cb418-107">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;</span></span>  
  
- <span data-ttu-id="cb418-108">SMTP サーバー名の長さは 256 文字を超えない必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb418-108">The length of the SMTP server name must not exceed 256 characters.</span></span>  
  
  <span data-ttu-id="cb418-109">SMTP アダプターは常に、前述の規則を使用して、デザイン時に SMTP ホスト名を検証します。</span><span class="sxs-lookup"><span data-stu-id="cb418-109">The SMTP adapter always validates the SMTP host name at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="cb418-110">さらに、SMTP アダプタは、SMTP アダプターで動的ポート経由でメッセージが送信される場合、実行時に SMTP ホスト名を検証します。</span><span class="sxs-lookup"><span data-stu-id="cb418-110">In addition, the SMTP adapter validates the SMTP host name at run time if a message is sent through a dynamic port with the SMTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb418-111">参照</span><span class="sxs-lookup"><span data-stu-id="cb418-111">See Also</span></span>  
 [<span data-ttu-id="cb418-112">SMTP アダプター構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="cb418-112">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)