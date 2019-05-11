---
title: AS2 のプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a28531d-da25-4f31-a822-734644d4bbd8
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9117ba9f81ff3b8f378d1562080e95ff4a2f79c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356299"
---
# <a name="configuring-as2-properties"></a><span data-ttu-id="dbceb-102">AS2 のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="dbceb-102">Configuring AS2 Properties</span></span>
<span data-ttu-id="dbceb-103">BizTalk Server は、AS2 プロパティを使用して、HTTP/HTTPS トランスポート経由の受信および送信 EDIINT/AS2 エンコード メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="dbceb-103">BizTalk Server uses AS2 properties to process incoming and outgoing EDIINT/AS2-encoded messages over HTTP/HTTPS transport.</span></span> <span data-ttu-id="dbceb-104">ここでは、AS2 メッセージ トランスポート用のパーティを作成する方法、およびパーティ間の AS2 アグリーメントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbceb-104">This section describes how to create parties for AS2 message transport and how to create AS2 agreements between the parties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbceb-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dbceb-105">In This Section</span></span>  
  
-   [<span data-ttu-id="dbceb-106">パーティの全般プロパティの構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="dbceb-106">Configuring General Party Properties (AS2)</span></span>](../core/configuring-general-party-properties-as2.md)  
  
-   [<span data-ttu-id="dbceb-107">ビジネス プロファイル プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="dbceb-107">Configuring Business Profile Properties</span></span>](../core/configuring-business-profile-properties.md)  
  
-   [<span data-ttu-id="dbceb-108">AS2 アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="dbceb-108">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)  
  
-   [<span data-ttu-id="dbceb-109">別のアグリーメント プロパティの再利用</span><span class="sxs-lookup"><span data-stu-id="dbceb-109">Reusing Properties from Another Agreement</span></span>](../core/reusing-properties-from-another-agreement.md)  
  
## <a name="see-also"></a><span data-ttu-id="dbceb-110">参照</span><span class="sxs-lookup"><span data-stu-id="dbceb-110">See Also</span></span>  
 <span data-ttu-id="dbceb-111">[AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md) </span><span class="sxs-lookup"><span data-stu-id="dbceb-111">[The Role of Agreements in AS2 Processing](../core/the-role-of-agreements-in-as2-processing.md) </span></span>  
 <span data-ttu-id="dbceb-112">[受信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-incoming-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="dbceb-112">[Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md) </span></span>  
 [<span data-ttu-id="dbceb-113">送信 AS2 メッセージのアグリーメントの解決</span><span class="sxs-lookup"><span data-stu-id="dbceb-113">Agreement Resolution for Outgoing AS2 Messages</span></span>](../core/agreement-resolution-for-outgoing-as2-messages.md)