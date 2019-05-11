---
title: 手順 5:スキーマ プロパティの昇格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa148fee56ae62d5c14112c850f16b4d9ae3cf53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288063"
---
# <a name="step-5-promote-schema-properties"></a>手順 5:スキーマ プロパティを昇格させる
この手順でスキーマのプロパティを昇格するように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、後の手順で作成したこれらのプロパティ値を参照できます。 プロモーションは、メッセージ インスタンス内の特定の値を参照しにアクセスできるようにするために使用するメカニズム[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントやオーケストレーションなど、コンテンツ ベース ルーティングを行うのためです。 さらに、昇格させたプロパティがで Microsoft IntelliSense の式エディターに表示される[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 監査と BizTalk 状態と動作状況の追跡 (HAT) ツールを使用してログ記録機能は、唯一の昇格させたスキーマ プロパティを追跡できます。  
  
### <a name="to-promote-schema-properties"></a>スキーマのプロパティを昇格するには  
  
1. ソリューション エクスプ ローラーで  **BTAHL7 プロジェクト**をダブルクリック、 **DoorBell.xsd**ノードがスキーマを開きます。  
  
2. 右クリックし、 **FirstName**要素のフィールドをポイントして、**昇格**、 をクリックし、**クイック昇格**します。  
  
3. クリックして**OK**プロパティ スキーマをプロジェクトに追加します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] アイコンにオレンジ色の円を追加、 **FirstName**要素が昇格されていることを示す要素。  
  
4. 次のフィールドの要素を昇格させる手順を繰り返します。  
  
   -   **MiddleName**  
  
   -   **LastName**  
  
   -   **SSN**  
  
   > [!IMPORTANT]
   >  その昇格患者 ID (PID) など、社会保障番号 (SSN) と、注意することが重要[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムからのすべての受信メッセージのプロパティを追跡するためにします。 このような状況の副作用は、メッセージの追跡データベースが患者 SSNs のコピーを保持することです。 これは、重大なセキュリティの問題を作成できます。 細心の注意とこのデータ ストアを保護するか、または PID データの昇格を完全に回避する必要があります。  
  
    昇格させたスキーマ要素に基づいてドキュメントの追跡の詳細については、正常性と動作状況の追跡について BizTalk Server のヘルプを参照してください。  
  
   続行する[手順 6。スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)