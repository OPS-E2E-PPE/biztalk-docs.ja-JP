---
title: BIC BEI 国通貨の検証ルールの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5526f96b9f60a53bb86b2aed1fc70352f71b57f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378333"
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a>BIC BEI/国/通貨の検証規則を展開します。
**BIC BEI/国/通貨の検証ルールを展開します。**  
  
1.  次の一連のポリシー、% プログラム files%\Microsoft BizTalk Accelerator for 発行され、個別に展開されているジェネリックとないメッセージの特定、必要である SWIFT\SDK\MX Messages\Base ポリシーでは、ビジネス ルール エンジン展開ウィザードを使用します。  
  
    -   MX_BIC_Master_Policy.xml  
  
    -   MX_BIC_Validation_Policy.xml  
  
    -   MX_BEI_Validation_Policy.xml  
  
    -   MX_DBConnection_Master_Policy.xml  
  
    -   MX_BICPlusIBAN_Validation_Policy.xml  
  
    -   MX_SEPA_Validation_Policy.xml  
  
2.  これらのポリシーを展開する前に MX_DBConnection_Master_Policy.xml と MX_BIC_Master_Policy.xml 必要があります、データベース サーバー名とデータベース名、国/通貨の値が格納されています。  
  
3.  すべて発行マスタ ポリシーが変更されていると、ビジネス ルール エンジン展開ウィザードを使用してポリシーします。 次のオプションを使用します。ポリシー/ボキャブラリ ファイルをデータベースにインポートします。  
  
4.  [プログラム]、[BizTalk サーバー] をクリックして\<バージョン\>をビジネス ルール作成ツールをクリックし、発行、6 つを展開し、ポリシーします。