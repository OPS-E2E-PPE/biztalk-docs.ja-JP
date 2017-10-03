---
title: "環境の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c91221162cccb7b6821c0edad12f8e76de2f10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-environment"></a>環境の設定
**環境を設定します。**  
  
1.  SWIFT メッセージ パックが構成されていることを確認してください。 同じ構成に Swift メッセージ パックのマニュアルを参照してください。  
  
2.  SQL スクリプトを実行*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql です。 Swift および MessagePack が A4Swift 以外のデータベース名に対して構成されている場合は、sql スクリプトのデータベース名を変更します。  
  
3.  コンピューター名とキー データベース名として"database"キー「データ ソース」の値を設定 (対象の Swift および MessagePack が構成されている) ファイルに*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator 用SWIFT\SDK\Tools\DataImport\DataImport.exe.config です。  
  
    > [!NOTE]
    >  データの入力ファイルは、DataImport.exe ファイルと同じフォルダーにすることはできません。  
  
4.  BICplusIBAN と SEPA テーブル内のデータをインポートするインポート ユーティリティを実行します。