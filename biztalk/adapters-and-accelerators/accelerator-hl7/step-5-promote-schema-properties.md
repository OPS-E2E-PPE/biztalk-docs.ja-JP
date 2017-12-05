---
title: "手順 5: スキーマのプロパティを昇格させる |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d68ece5bedf7ec46a6d5ede7efc6878fa972fc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-5-promote-schema-properties"></a>手順 5: スキーマのプロパティを昇格させる
このステップでは、スキーマ プロパティを昇格できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、後の手順で作成するこれらのプロパティ値を参照できます。 プロモーションはメッセージのインスタンス内で特定の値を参照しにアクセスできるようにするために使用メカニズム[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントやオーケストレーションなど、コンテンツ ベース ルーティングの目的。 さらに、昇格させたプロパティでは表示[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]の式エディターでの IntelliSense[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]監査と BizTalk 状態と動作状況の追跡 (HAT) ツールを使用してログ記録機能は、唯一の昇格させたスキーマ プロパティを追跡できます。  
  
### <a name="to-promote-schema-properties"></a>スキーマ プロパティを昇格するには  
  
1.  ソリューション エクスプ ローラーで、 **BTAHL7 プロジェクト**をダブルクリックして、 **DoorBell.xsd**を開くには、スキーマのノードです。  
  
2.  右クリックし、 **FirstName**要素のフィールドをポイントし、**昇格**、クリックして**クイック昇格**です。  
  
3.  をクリックして**OK**プロパティ スキーマをプロジェクトに追加します。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アイコンにオレンジ色の円を追加、 **FirstName**要素を昇格されていることを示す要素。  
  
4.  次のフィールドの要素を昇格させるには、この手順を繰り返します。  
  
    -   **MiddleName**  
  
    -   **[氏名]**  
  
    -   **SSN**  
  
    > [!IMPORTANT]
    >  その昇格患者の ID (PID) 社会保障番号 (SSN) などを確認することが重要[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をシステムからのすべての受信メッセージのプロパティを追跡します。 このような状況の副作用は、メッセージの追跡データベースが患者 SSNs のコピーを保持することです。 これは、重要なセキュリティ上の問題を作成できます。 このデータ ストアに細心の注意を保護するか、または PID データの昇格を完全に回避する必要があります。  
  
     昇格させたスキーマ要素に基づいてドキュメントの追跡の詳細については、正常性と動作状況の追跡について BizTalk Server ヘルプを参照してください。  
  
 進みます[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)