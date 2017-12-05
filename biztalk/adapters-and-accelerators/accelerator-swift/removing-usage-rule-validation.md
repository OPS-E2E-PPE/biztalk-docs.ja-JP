---
title: "使用量ルールの検証を削除する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017184e5f530096dc0ca166fdaaa9810a3372cfa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="removing-usage-rule-validation"></a>使用量ルールの検証を削除します。
使用に関する規則は SWIFT 標準で定義され、によって強制[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージの種類ごとに固有のビジネス ポリシー。 これらの使用に関する規則は、使用できるフィールドの追加の検証を提供するガイドラインを示します。 ネットワーク検証ルールは、必須とは異なり、メッセージ型の使用状況規則を必要とならないを選択できます。 場合がある場合は、次のいずれかの操作を行います。  
  
-   メッセージの種類の検証ポリシーから使用状況規則を適用する特定のビジネス ルールを削除することができます。  
  
    > [!IMPORTANT]
    >  ポリシーから、ルールの削除が完全に削除されます。  
  
-   いずれかの使用状況規則を適用しないようにする場合は、メッセージの種類の検証ポリシーを展開解除することができます。  
  
### <a name="to-remove-a-rule-from-a-policy"></a>ポリシーのルールを削除するには  
  
1.  メモ帳などのテキスト エディターで開いて検証ポリシーで MT103_Validation_Policy など、変更する*\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category 1\MT103 です。  
  
2.  できませんし、ポリシーを保存し、ルール ノードを削除します。  
  
3.  ビジネス ルール エンジン展開ウィザードを使用して、公開したり、ポリシーを展開します。  
  
    > [!NOTE]
    >  ポリシーのコピーを作成する、特定の規則を削除して、変更されたポリシーを展開し、検証ポリシーからルールを削除することもできます。 以前のバージョンのポリシーを展開解除します。  
  
    > [!NOTE]
    >  ビジネス ルール作成ツールには、パブリッシュまたは配置済みのポリシーから規則を削除することはできません。  
  
### <a name="to-remove-the-policy-for-a-message-type"></a>メッセージの種類のポリシーを削除するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
2.  ポリシー エクスプ ローラーには、MT103_Validation_Policy など、メッセージの種類の展開の検証ポリシーを検索します。  
  
3.  ポリシーを右クリックし、をクリックして**Undeploy**、 をクリックして**削除**、順にクリック**はい**です。