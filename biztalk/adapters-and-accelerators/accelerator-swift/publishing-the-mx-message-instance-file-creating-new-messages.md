---
title: MX メッセージ インスタンス ファイル (新しいメッセージの作成) の発行 |Microsoft Docs
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
ms.openlocfilehash: 21c7894158bb245b746b9a53dcfc93d40b9f9e1d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970683"
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a><span data-ttu-id="52c44-102">MX メッセージ インスタンス ファイル (新しいメッセージの作成) の発行</span><span class="sxs-lookup"><span data-stu-id="52c44-102">Publishing the MX Message Instance File (Creating New Messages)</span></span>
<span data-ttu-id="52c44-103">**MX メッセージ インスタンスのファイルを発行するには。**</span><span class="sxs-lookup"><span data-stu-id="52c44-103">**To publish the MX message instance file:**</span></span>  

1. <span data-ttu-id="52c44-104">前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して **.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-104">Go to output folder of the InfoPath form template generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span>  

2. <span data-ttu-id="52c44-105">Internet Explorer で開く **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-105">In Internet Explorer, open **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.</span></span>  

3. <span data-ttu-id="52c44-106">新しい Swift MX メッセージ ウィンドウで、クリックして**アップロード**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-106">In New Swift MX Messages window, click **Upload**.</span></span>  

4. <span data-ttu-id="52c44-107">ドキュメントのアップロード] ウィンドウで、[**参照**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-107">In the Upload Document window, click **Browse**.</span></span>  

5. <span data-ttu-id="52c44-108">ファイルの選択 ダイアログ ボックスで、前の手順で生成された InfoPath フォームの出力フォルダーに移動 **.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-108">In the Choose file dialog box, move to the output folder of the InfoPath form generated in the previous step **..\\<MessageType\>\TemplateDS\InfoPath Form Template**.</span></span> <span data-ttu-id="52c44-109">選択、 \<MessageType\>.xml pacs.004.001.01.xml などのファイルをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-109">Select the \<MessageType\>.xml file such as pacs.004.001.01.xml, and then click **Open**.</span></span>  

6. <span data-ttu-id="52c44-110">ドキュメントのアップロード] ウィンドウで、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="52c44-110">In the Upload Document window, click **OK**.</span></span>  

7. <span data-ttu-id="52c44-111">新規 SWIFT MX メッセージ: \<MessageType\> Namespace ボックスで、型のウィンドウ<strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\></strong>、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="52c44-111">In the New SWIFT MX Messages: \<MessageType\> window, in the Namespace box, type <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\></strong>, and then click **OK**.</span></span>
