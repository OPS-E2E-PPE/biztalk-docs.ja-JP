---
title: (新しいメッセージの作成) MT メッセージ インスタンスのファイルをパブリッシュ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52118d20-f325-432a-9e3e-5cc10232cba0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 390fe7602a3b3fafe547938ff07f6290f3453196
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377082"
---
# <a name="publishing-the-mt-message-instance-file-creating-new-messages"></a><span data-ttu-id="5211f-102">(新しいメッセージの作成) MT メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="5211f-102">Publishing the MT Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="5211f-103">**ファイルをパブリッシュ MT メッセージ インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="5211f-103">**To publish the MT message instance file:**</span></span>  
  
1.  <span data-ttu-id="5211f-104">前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して **.\MTXXX\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-104">Go to output folder of the InfoPath form template generated in the previous step **..\MTXXX\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="5211f-105">Internet Explorer で開く **http://localhost/sites/BASSite/New%20SWIFT%20MT%20Messages**します。</span><span class="sxs-lookup"><span data-stu-id="5211f-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MT%20Messages**.</span></span>  
  
3.  <span data-ttu-id="5211f-106">新しい Swift MT メッセージ ウィンドウで **アップロード**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-106">In New Swift MT Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="5211f-107">ドキュメントのアップロード] ウィンドウで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="5211f-108">ファイルの選択 ダイアログ ボックスで前の手順で作成した InfoPath 形式の出力フォルダーに移動 **.\MTXXX\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\MTXXX\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="5211f-109">MT103.xml など MTXXX.xml ファイルを選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-109">Select the MTXXX.xml file such as MT103.xml and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="5211f-110">ドキュメントのアップロード] ウィンドウで、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="5211f-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="5211f-111">SWIFT MT の新しいメッセージ。MTXXX ウィンドウで、Namespace ボックスに「 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="5211f-111">In the New SWIFT MT Messages: MTXXX window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**, and then click **OK**.</span></span>