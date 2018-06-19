---
title: アプリケーションへの参照を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db190fab-c8e6-4f2e-8999-f6f9479460f0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b28baa30f0c6af03a95917ee752b1a69f23aae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297810"
---
# <a name="how-to-add-a-reference-to-an-application"></a><span data-ttu-id="95bcf-102">アプリケーションへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="95bcf-102">How to Add a Reference to an Application</span></span>
<span data-ttu-id="95bcf-103">このトピックは、別のアプリケーションへの参照を追加する BizTalk Server 管理コンソールの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="95bcf-103">This topic provides information about using the BizTalk Server Administration console to add a reference from one application to another.</span></span> <span data-ttu-id="95bcf-104">同じ BizTalk グループの別のアプリケーション内に既に存在するアイテムを、現在のアプリケーションで使用する場合は、参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="95bcf-104">You add a reference when you want to use an artifact in the current application that already exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="95bcf-105">EDI 固有のスキーマ、パイプライン、および BizTalk アプリケーション 1 などの別のアプリケーションからオーケストレーション (BizTalk EDI アプリケーションに展開) を使用する場合は、BizTalk EDI アプリケーションへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95bcf-105">If you want to use the EDI-specific schemas, pipelines, and orchestrations (deployed in the BizTalk EDI Application) from another application such as BizTalk Application 1, you must add a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="95bcf-106">カスタム アイテムを BizTalk EDI アプリケーションに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="95bcf-106">You should not add custom artifacts to the BizTalk EDI Application.</span></span>  
  
 <span data-ttu-id="95bcf-107">詳細については。</span><span class="sxs-lookup"><span data-stu-id="95bcf-107">For information about:</span></span>  
  
-   <span data-ttu-id="95bcf-108">別のアプリケーションへの参照を追加するを参照してください[を別のアプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkID=155011)(http://go.microsoft.com/fwlink/?LinkID=155011)。</span><span class="sxs-lookup"><span data-stu-id="95bcf-108">Adding a reference to another application, see [How to Add a Reference to Another Application](http://go.microsoft.com/fwlink/?LinkID=155011) (http://go.microsoft.com/fwlink/?LinkID=155011).</span></span>  
  
-   <span data-ttu-id="95bcf-109">参照を追加する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI アプリケーションを参照してください[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkId=155026)(http://go.microsoft.com/fwlink/?LinkId=155026)。</span><span class="sxs-lookup"><span data-stu-id="95bcf-109">Adding a reference to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI application, see [How to Add a Reference to the BizTalk Server EDI Application](http://go.microsoft.com/fwlink/?LinkId=155026) (http://go.microsoft.com/fwlink/?LinkId=155026).</span></span>