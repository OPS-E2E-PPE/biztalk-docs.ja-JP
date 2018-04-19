---
title: (新しいメッセージの作成) MX メッセージ インスタンスのファイルをパブリッシュ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082174428f177905527d0c648b4d7ad000dde36
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a><span data-ttu-id="4c45d-102">(新しいメッセージの作成) MX メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="4c45d-102">Publishing the MX Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="4c45d-103">**ファイルをパブリッシュ MX メッセージ インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="4c45d-103">**To publish the MX message instance file:**</span></span>  
  
1.  <span data-ttu-id="4c45d-104">前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して**.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-104">Go to output folder of the InfoPath form template generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span>  
  
2.  <span data-ttu-id="4c45d-105">Internet Explorer で、開く **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span></span>  
  
3.  <span data-ttu-id="4c45d-106">新しい Swift MX メッセージ ウィンドウで **アップロード**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-106">In New Swift MX Messages window, click **Upload**.</span></span>  
  
4.  <span data-ttu-id="4c45d-107">ドキュメントのアップロード] ウィンドウで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-107">In the Upload Document window, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="4c45d-108">ファイルの選択 ダイアログ ボックスで前の手順で作成した InfoPath 形式の出力フォルダーに移動**.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="4c45d-109">選択、 \<MessageType\>.xml pacs.004.001.01.xml などのファイルおよびクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-109">Select the \<MessageType\>.xml file such as pacs.004.001.01.xml, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="4c45d-110">ドキュメントのアップロード] ウィンドウで、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="4c45d-110">In the Upload Document window, click **OK**.</span></span>  
  
7.  <span data-ttu-id="4c45d-111">新規 SWIFT MX メッセージで: \<MessageType\> Namespace ボックスで、型のウィンドウ **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_ \<MessageType\>**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="4c45d-111">In the New SWIFT MX Messages: \<MessageType\> window, in the Namespace box, type **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\>**, and then click **OK**.</span></span>