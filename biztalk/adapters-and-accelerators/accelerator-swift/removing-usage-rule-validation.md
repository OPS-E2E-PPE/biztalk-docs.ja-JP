---
title: 使用規則の検証を削除する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e5ffc3e1ca36e200055a26e8e78f341b125d8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975547"
---
# <a name="removing-usage-rule-validation"></a>使用規則の検証を削除します。
使用に関する規則は SWIFT 標準で定義され、によって適用される[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージの種類ごとに固有のビジネス ポリシー。 これらの使用に関する規則では、フィールドの追加の検証を提供する際のガイドラインを示します。 必須のネットワークの検証規則とは異なり、メッセージ型の使用に関する規則を必要としないを選択できます。 ケースがある場合は、次のいずれかの操作を行います。  

-   メッセージの種類の検証ポリシーから使用状況規則を適用する特定のビジネス ルールを削除することができます。  

    > [!IMPORTANT]
    >  ポリシーから、ルールの削除が完全に削除されます。  

-   使用状況規則を適用しない場合のメッセージの種類の検証ポリシーの展開を解除できます。  

### <a name="to-remove-a-rule-from-a-policy"></a>ポリシーのルールを削除するには  

1.  メモ帳などのテキスト エディターで、たとえばで MT103_Validation_Policy を変更する検証ポリシーを開きます*\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \ProgramFiles\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MT103 します。  

2.  できませんし、ポリシーを保存ルール ノードを削除します。  

3.  ビジネス ルール エンジン展開ウィザードを使用して、発行し、ポリシーを展開します。  

    > [!NOTE]
    >  ポリシーのコピーを作成する、特定のルールを削除して、変更したポリシーを展開し、検証ポリシーからルールを削除することもできます。 以前のバージョンのポリシーを展開解除します。  

    > [!NOTE]
    >  ビジネス ルール作成ツールでは、発行またはデプロイされたポリシーからルールを削除できません。  

### <a name="to-remove-the-policy-for-a-message-type"></a>メッセージの種類のポリシーを削除するには  

1. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。  

2. ポリシー エクスプ ローラーでは、メッセージの種類、MT103_Validation_Policy などの展開の検証ポリシーを紹介します。  

3. ポリシーを右クリックし、をクリックして**Undeploy**、 をクリックして**削除**、順にクリックします**はい**します。
