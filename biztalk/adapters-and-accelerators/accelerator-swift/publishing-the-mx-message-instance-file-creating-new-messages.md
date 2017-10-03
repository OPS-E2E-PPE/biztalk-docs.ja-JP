---
title: "(新しいメッセージの作成) MX メッセージ インスタンスのファイルをパブリッシュ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108153e362480c272d1f772ea4e97c66c6894358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a><span data-ttu-id="fa04f-102">(新しいメッセージの作成) MX メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="fa04f-102">Publishing the MX Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="fa04f-103">**ファイルをパブリッシュ MX メッセージ インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="fa04f-103">**To publish the MX message instance file:**</span></span>  
  
1.  <span data-ttu-id="fa04f-104">前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して**.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-104">Go to output folder of the InfoPath form template generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="fa04f-105">Internet Explorer で、開く**http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span></span>  
  
3.  <span data-ttu-id="fa04f-106">新しい Swift MX メッセージ ウィンドウで **アップロード**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-106">In New Swift MX Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="fa04f-107">ドキュメントのアップロード] ウィンドウで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="fa04f-108">ファイルの選択 ダイアログ ボックスで前の手順で作成した InfoPath 形式の出力フォルダーに移動**.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="fa04f-109">選択、 \<MessageType > .xml pacs.004.001.01.xml などのファイルおよびクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-109">Select the \<MessageType>.xml file such as pacs.004.001.01.xml, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="fa04f-110">ドキュメントのアップロード] ウィンドウで、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="fa04f-111">新規 SWIFT MX メッセージで: \<MessageType > Namespace ボックスで、型のウィンドウ**http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX _\<MessageType >**、およびをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fa04f-111">In the New SWIFT MX Messages: \<MessageType> window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType>**, and then click **OK**.</span></span>