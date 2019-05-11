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
ms.openlocfilehash: 59c5dca63e5d4120aad364afe6ca2da740196ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251283"
---
# <a name="create-the-dsrtxt-file"></a>DSR.txt ファイルを作成します。
応答 DSR.txt メッセージ ファイルを作成するのにには、次の手順を使用します。 このチュートリアルのシナリオを確認するのには、このファイルを後で使用します。  
  
### <a name="to-create-the-dsrtxt-file"></a>DSR.txt ファイルを作成するには  
  
1. メモ帳などのエディターを開き、エディターに次のテキストをコピーします。  
  
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
  
2. ファイルに保存します**DSR.txt**で、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative のアクセラレータチュートリアルのフォルダーと、エディターを閉じます。  
  
   続行する[手順 1。作成および展開の一般的なヘッダーと確認スキーマ](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)します。