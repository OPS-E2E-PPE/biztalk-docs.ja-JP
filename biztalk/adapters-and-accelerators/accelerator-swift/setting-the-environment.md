---
title: 環境の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f0c63671833a394e0c750561d90c12c6476515f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961896"
---
# <a name="setting-the-environment"></a>環境の設定
**環境を設定します。**  
  
1.  SWIFT メッセージ パックが構成されていることを確認してください。 同じ構成に Swift メッセージ パックのマニュアルを参照してください。  
  
2.  SQL スクリプトを実行*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql です。 Swift および MessagePack が A4Swift 以外のデータベース名に対して構成されている場合は、sql スクリプトのデータベース名を変更します。  
  
3.  コンピューター名とキー データベース名として"database"キー「データ ソース」の値を設定 (対象の Swift および MessagePack が構成されている) ファイルに*\<ドライブ\>*: \Program Files\Microsoft BizTalkSWIFT\SDK\Tools\DataImport\DataImport.exe.config のアクセラレータです。  
  
    > [!NOTE]
    >  データの入力ファイルは、DataImport.exe ファイルと同じフォルダーにすることはできません。  
  
4.  BICplusIBAN と SEPA テーブル内のデータをインポートするインポート ユーティリティを実行します。