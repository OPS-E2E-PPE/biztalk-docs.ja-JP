---
title: Tutorial2 を使用する準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d790a53576c4f153265531fca974089eb5292a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978659"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="bc8f4-102">チュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="bc8f4-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="bc8f4-103">このチュートリアルを使用する前に、ADT^A03.txt ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-103">Before you use the tutorial, you need to create an ADT^A03.txt file.</span></span>  
  
### <a name="to-create-the-adta03txt-file"></a><span data-ttu-id="bc8f4-104">ADT^A03.txt ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="bc8f4-104">To create the ADT^A03.txt file</span></span>  
  
1. <span data-ttu-id="bc8f4-105">メモ帳などのエディターを開き、エディターに次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-105">Open an editor such as Notepad and copy the following text into the editor:</span></span>  
  
   ```  
   MSH|^~\&|Tutorial_ADTSystem|MCM|BTAHL7InterfaceEngine||199601121005||ADT^A03|000001|P|2.3.1  
   EVN|A03|199601121005||01||199601121000  
   PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||  
       123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
   PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|  
      NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P  
      ^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString  
      ^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString  
      ^Test^Test^NormalString^Test|N  
   PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="bc8f4-106">5 つの行で、.txt ファイルを 1 つずつ存在する必要がありますが、"MSH"、"EVN"、"PID"、"PD1"および"PV1"で始まります。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-106">There should be five lines in the .txt file, one each starting with "MSH", "EVN", "PID", "PD1", and "PV1".</span></span> <span data-ttu-id="bc8f4-107">"PID"行と"PD1"の行でスペースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-107">You will need to remove the spaces within the "PID" line and the "PD1" line.</span></span> <span data-ttu-id="bc8f4-108">必要に応じて、メモ帳での折り返しを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-108">If necessary, turn off word wrap in Notepad.</span></span>  
  
2. <span data-ttu-id="bc8f4-109">ファイルに保存します**ADT^A03.txt**で、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>のアクセラレータHL7\SDK\End ツー エンド チュートリアル フォルダー、および終値のメモ帳。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-109">Save the file as **ADT^A03.txt** in the \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder, and then close Notepad.</span></span>  
  
   <span data-ttu-id="bc8f4-110">進みます[手順 1: ヘッダーと確認スキーマ作成して展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc8f4-110">Proceed to [Step 1: Create and Deploy Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md).</span></span>