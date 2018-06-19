---
title: スキーマ プロジェクトを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207210"
---
# <a name="creating-a-schema-project"></a>スキーマ プロジェクトを作成します。
スキーマのプロジェクトを作成するには  
  
1.  Visual Studio では、SWIFT MX スキーマの BizTalk プロジェクトを作成します。  
  
2.  適切な MX (ISO20022 サイトからダウンロード) をスキーマにテストするには、このプロジェクトに追加します。  
  
3.  上記のメッセージの種類に対応するエンベロープ スキーマを展開する必要がありますし、上記の MX メッセージの Message Repair and New Submission の機能を実行する場合は、それ以外の場合手順 6. に進みます。  
  
    > [!NOTE]
    >  MX エンベロープ スキーマを生成する方法については、フォーム ジェネレーターは、ドキュメントを参照してください。  
  
4.  SWIFT MX スキーマ プロジェクトには、エンベロープ スキーマを追加します。  
  
5.  BizTalk エディターで、エンベロープ スキーマを開き、"CorrelationToken"および"IsNewSubmission"プロパティを昇格します。 上記のフィールドを右クリックし、をクリックして**昇格クイック昇格]-> [** をこれらのプロパティを昇格させます。  
  
    > [!NOTE]
    >  スキーマのプロパティを昇格する方法の詳細については、BizTalk Server のマニュアルを参照してください。  
  
6.  (Sn – k key.snk を使用)、キー ファイルを作成し、強力なを作成するプロジェクトに割り当てます、名前のアセンブリ。  
  
7.  プロジェクトをビルドし、展開します。