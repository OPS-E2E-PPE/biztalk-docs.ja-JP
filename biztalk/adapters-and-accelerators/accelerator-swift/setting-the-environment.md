---
title: 環境の設定 |Microsoft Docs
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
ms.openlocfilehash: c2bcff19cb26482c566820956f93642887b43015
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530095"
---
# <a name="setting-the-environment"></a>環境の設定
**環境を設定します。**  
  
1.  SWIFT メッセージ パックが構成されていることを確認します。 同じ構成に Swift メッセージ パックのマニュアルを参照してください。  
  
2.  SQL スクリプトを実行*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql します。 Swift および MessagePack は A4Swift 以外のデータベース名で構成されている場合は、sql スクリプト内のデータベース名を変更します。  
  
3.  コンピューター名とデータベース名として"database"キーとして「データ ソース」のキーの値を設定 (を Swift および MessagePack が構成されている) ファイルに*\<ドライブ\>*: \Program Files\Microsoft BizTalkSWIFT\SDK\Tools\DataImport\DataImport.exe.config のアクセラレータです。  
  
    > [!NOTE]
    >  データの入力ファイルは、DataImport.exe ファイルと同じフォルダーにすることはできません。  
  
4.  BICplusIBAN と SEPA テーブル内のデータをインポートするデータ インポート ユーティリティを実行します。