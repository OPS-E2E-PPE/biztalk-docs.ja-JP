---
title: "スキーマ XSD を使用してメッセージ インスタンスの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eda0b76b3daff53290264169c5b2effe80a9e5c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="84f22-102">スキーマ XSD を使用してメッセージ インスタンスの検証</span><span class="sxs-lookup"><span data-stu-id="84f22-102">Validating a Message Instance Using the Schema XSD</span></span>
<span data-ttu-id="84f22-103">ここでは、Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] によって RNPIP アセンブリ ファイルに構築したスキーマ XSD ファイルを使用してメッセージ インスタンスを検証する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="84f22-103">This topic describes how to validate a message instance using one of the schema XSD files that Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] has built into the RNPIPs assembly file.</span></span>  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="84f22-104">スキーマ XSD を使用してメッセージ インスタンスを検証するには</span><span class="sxs-lookup"><span data-stu-id="84f22-104">To validate a message instance using the schema XSD</span></span>  
  
1.  <span data-ttu-id="84f22-105">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-105">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="84f22-106">**ファイル**、 をポイント**開く**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-106">On the **File**, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="84f22-107">検索*\<ドライブ\>*\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas をクリックして**RNPIPs.btproj**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-107">Locate *\<drive\>*\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="84f22-108">ソリューション エクスプ ローラーで、 **Rnpip**、クリックして、メッセージ インスタンスの検証に使用する XSD スキーマを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-108">In Solution Explorer, expand **RNPIPs**, right-click the schema XSD that you want to use to validate a message instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="84f22-109">[プロパティ ページ] ダイアログ ボックスで、**入力インスタンス ファイル名**、ファイルが含まれているフォルダーを探し、メッセージ インスタンス XML ファイルを選択およびクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-109">In the Property Pages dialog box, click **Input Instance Filename**, locate the folder that contains the file, select the message instance XML file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="84f22-110">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84f22-110">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="84f22-111">ソリューション エクスプ ローラーでスキーマを右クリックして、クリックして、メッセージ インスタンスの検証に使用する XSD**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="84f22-111">In Solution Explorer, right-click the schema XSD that you want to use to validate a message instance, and then click **Validate Instance**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f22-112">参照</span><span class="sxs-lookup"><span data-stu-id="84f22-112">See Also</span></span>  
 <span data-ttu-id="84f22-113">[Rnpip の既存の PIP の変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span><span class="sxs-lookup"><span data-stu-id="84f22-113">[Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span></span>  
 [<span data-ttu-id="84f22-114">PIP の操作</span><span class="sxs-lookup"><span data-stu-id="84f22-114">Working with PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)