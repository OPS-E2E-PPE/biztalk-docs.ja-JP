---
title: スキーマ プロジェクトの作成 |Microsoft Docs
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
ms.openlocfilehash: 4a6419c008a95277256c75fbd0b7d6dda388061f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378457"
---
# <a name="creating-a-schema-project"></a>スキーマ プロジェクトの作成
スキーマ プロジェクトを作成するには  
  
1.  Visual Studio では、SWIFT MX スキーマの BizTalk プロジェクトを作成します。  
  
2.  このプロジェクトに適切な MX スキーマ (ISO20022 サイトからダウンロード) をテストするには、これを追加します。  
  
3.  上記のメッセージの種類に対応するエンベロープ スキーマを展開する必要がありますし、上記の MX メッセージの Message Repair and New Submission の機能を実行する場合は、それ以外の場合手順 6 に進みます。  
  
    > [!NOTE]
    >  MX エンベロープ スキーマを生成する方法については、フォーム ジェネレーターのマニュアルを参照してください。  
  
4.  エンベロープ スキーマは、SWIFT MX スキーマ プロジェクトに追加します。  
  
5.  BizTalk エディターで、エンベロープ スキーマを開き、"CorrelationToken"と"IsNewSubmission"プロパティを昇格します。 上記のフィールドを右クリックし、をクリックして**昇格クイック昇格]-> [** にこれらのプロパティを昇格します。  
  
    > [!NOTE]
    >  スキーマのプロパティを昇格させる方法の詳細については、BizTalk Server のマニュアルを参照してください。  
  
6.  (Sn – k key.snk を使用して) キー ファイルを作成し、強力なを作成するプロジェクトに割り当てます、という名前のアセンブリ。  
  
7.  ビルドし、プロジェクトを配置します。