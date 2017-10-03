---
title: "(新しいメッセージの作成) MT メッセージ インスタンスのファイルをパブリッシュ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52118d20-f325-432a-9e3e-5cc10232cba0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00ae6aabf2a51071d1dfe078914bc92487a6505e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-the-mt-message-instance-file-creating-new-messages"></a><span data-ttu-id="afd21-102">(新しいメッセージの作成) MT メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="afd21-102">Publishing the MT Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="afd21-103">**ファイルをパブリッシュ MT メッセージ インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="afd21-103">**To publish the MT message instance file:**</span></span>  
  
1.  <span data-ttu-id="afd21-104">前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して**.\MTXXX\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-104">Go to output folder of the InfoPath form template generated in the previous step **..\MTXXX\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="afd21-105">Internet Explorer で、開く**http://localhost/sites/BASSite/New%20SWIFT%20MT%20Messages**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MT%20Messages**.</span></span>  
  
3.  <span data-ttu-id="afd21-106">新しい Swift MT メッセージ ウィンドウで **アップロード**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-106">In New Swift MT Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="afd21-107">ドキュメントのアップロード] ウィンドウで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="afd21-108">ファイルの選択 ダイアログ ボックスで前の手順で作成した InfoPath 形式の出力フォルダーに移動**.\MTXXX\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\MTXXX\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="afd21-109">MT103.xml など MTXXX.xml ファイルを選択し、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-109">Select the MTXXX.xml file such as MT103.xml and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="afd21-110">ドキュメントのアップロード] ウィンドウで、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="afd21-111">SWIFT MT の新しいメッセージ: MTXXX ウィンドウの Namespace ボックスの入力で、 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="afd21-111">In the New SWIFT MT Messages: MTXXX window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**, and then click **OK**.</span></span>