---
title: SOAP 受信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], receive handlers
- SOAP adapters, receive handlers
- receive handlers, SOAP adapters
ms.assetid: e1174381-f36c-4131-83b7-26bfa879802e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4f9e63b1b41592cdda3dd984e85f20373fd2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968347"
---
# <a name="how-to-configure-a-soap-receive-handler"></a><span data-ttu-id="d95ac-102">SOAP 受信ハンドラを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d95ac-102">How to Configure a SOAP Receive Handler</span></span>
<span data-ttu-id="d95ac-103">BizTalk Server 管理コンソールを使用して、SOAP 受信ハンドラの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d95ac-103">You can configure the SOAP receive handler settings by using the BizTalk Server Administration Console.</span></span> <span data-ttu-id="d95ac-104">BizTalk Server 管理コンソールを使用してアダプターを構成する場合、ハンドラー オーバーライド プロパティを BizTalk エクスプローラで設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d95ac-104">If you configure the adapter using the BizTalk Server Administration Console, the handler override properties do not need to be set in BizTalk Explorer.</span></span>  
  
### <a name="to-change-global-variables-for-the-soap-receive-handler"></a><span data-ttu-id="d95ac-105">SOAP 受信ハンドラのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="d95ac-105">To change global variables for the SOAP receive handler</span></span>  
  
1. <span data-ttu-id="d95ac-106">BizTalk Server 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="d95ac-106">In the BizTalk Server Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="d95ac-107">展開したアダプターの一覧でクリックして**SOAP**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d95ac-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="d95ac-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d95ac-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95ac-109">参照</span><span class="sxs-lookup"><span data-stu-id="d95ac-109">See Also</span></span>  
 <span data-ttu-id="d95ac-110">[SOAP アダプターの構成](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d95ac-110">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="d95ac-111">Web サービスの利用</span><span class="sxs-lookup"><span data-stu-id="d95ac-111">Consuming Web Services</span></span>](../core/consuming-web-services.md)