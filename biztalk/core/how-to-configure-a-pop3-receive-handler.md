---
title: POP3 受信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, POP3 adapters
- POP3 adapters, receive handlers
- configuring [POP3 adapters], receive handlers
ms.assetid: 2191c201-545e-4d5a-a1ca-3c38c7b8258d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8868ce589fa7556da185dcaf4c71b5bfd5cae159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247786"
---
# <a name="how-to-configure-a-pop3-receive-handler"></a><span data-ttu-id="c0b1a-102">POP3 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c0b1a-102">How to Configure a POP3 Receive Handler</span></span>
<span data-ttu-id="c0b1a-103">次の手順を実行して、POP3 受信ハンドラーに関連付けられているホストを変更します。</span><span class="sxs-lookup"><span data-stu-id="c0b1a-103">Use the following procedure to change the host associated with the POP3 receive handler.</span></span>  
  
### <a name="to-configure-the-general-properties-for-a-pop3-receive-handler"></a><span data-ttu-id="c0b1a-104">POP3 受信ハンドラーの全般プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="c0b1a-104">To configure the general properties for a POP3 receive handler</span></span>  
  
1.  <span data-ttu-id="c0b1a-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="c0b1a-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="c0b1a-106">展開したアダプターの一覧でクリックして**POP3**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c0b1a-106">In the expanded adapter list, click **POP3**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c0b1a-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b1a-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="c0b1a-108">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0b1a-108">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b1a-109">参照</span><span class="sxs-lookup"><span data-stu-id="c0b1a-109">See Also</span></span>  
 [<span data-ttu-id="c0b1a-110">クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c0b1a-110">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)