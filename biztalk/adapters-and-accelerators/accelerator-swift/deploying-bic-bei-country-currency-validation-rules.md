---
title: "BIC BEI 国通貨検証規則を展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f1786b37194db25f0e38db7491538857f3406b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a>BIC、BEI、国/通貨検証規則を展開します。
**BIC、BEI、国/通貨の検証ルールを展開します。**  
  
1.  % プログラム files%\Microsoft BizTalk Accelerator for、SWIFT\SDK\MX Messages\Base ポリシーで発行および個別に展開されているように汎用的なメッセージに固有ではない、必要であり、ポリシーの次のセットでは、ビジネス ルール エンジン展開ウィザードを使用します。  
  
    -   MX_BIC_Master_Policy.xml  
  
    -   MX_BIC_Validation_Policy.xml  
  
    -   MX_BEI_Validation_Policy.xml  
  
    -   MX_DBConnection_Master_Policy.xml  
  
    -   MX_BICPlusIBAN_Validation_Policy.xml  
  
    -   MX_SEPA_Validation_Policy.xml  
  
2.  これらのポリシーを展開する前に MX_DBConnection_Master_Policy.xml と MX_BIC_Master_Policy.xml 指定してください、データベース サーバー名とデータベース名、国/通貨の値が格納されています。  
  
3.  マスターのポリシーが変更されている発行すべてビジネス ルール エンジン展開ウィザードを使用してポリシーします。 次のオプションを使用します。 ポリシー/ボキャブラリ ファイルをデータベースにインポートします。  
  
4.  [プログラム]、[BizTalk サーバー] をクリックして\<バージョン >、[ビジネス ルール作成ツール] をクリックし、発行、6 つのポリシーします。