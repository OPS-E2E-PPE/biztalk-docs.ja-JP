---
title: DSR.txt ファイルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6947af7-c5ce-4ee6-9fe9-5c1094d0aee0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f5fd535b1a4db0a960c8f993cd6daf22ee9d1b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976883"
---
# <a name="create-the-dsrtxt-file"></a><span data-ttu-id="43b2f-102">DSR.txt ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="43b2f-102">Create the DSR.txt File</span></span>
<span data-ttu-id="43b2f-103">応答 DSR.txt メッセージ ファイルを作成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="43b2f-103">Use the following procedure to create the response DSR.txt message file.</span></span> <span data-ttu-id="43b2f-104">このチュートリアルのシナリオを確認するのには、このファイルを後で使用します。</span><span class="sxs-lookup"><span data-stu-id="43b2f-104">You will use this file later to verify the tutorial scenario.</span></span>  
  
### <a name="to-create-the-dsrtxt-file"></a><span data-ttu-id="43b2f-105">DSR.txt ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="43b2f-105">To create the DSR.txt file</span></span>  
  
1. <span data-ttu-id="43b2f-106">メモ帳などのエディターを開き、エディターに次のテキストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="43b2f-106">Open an editor, such as Notepad, and copy the following text into the editor:</span></span>  
  
   ```  
   MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
   MSA|AA|MSG00003  
   QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
   DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
   DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
   DSP|||ELECTROLYTES  
   DSP||| SODIUM 136 [135-148] MEQ/L STAT  
   DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
   DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
   DSP||| CO2 25 [20-30] MEQ/L STAT  
   DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
   ```  
  
2. <span data-ttu-id="43b2f-107">ファイルに保存します**DSR.txt**で、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative のアクセラレータチュートリアルのフォルダーと、エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="43b2f-107">Save the file as **DSR.txt** in the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder, and then close the editor.</span></span>  
  
   <span data-ttu-id="43b2f-108">進みます[手順 1: 一般的なヘッダーと確認スキーマ作成して展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="43b2f-108">Proceed to [Step 1: Create and Deploy Common Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md).</span></span>