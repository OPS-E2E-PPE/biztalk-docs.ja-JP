---
title: クロス フィールド検証の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cd14497f08bf085c1a93122baa00875ad714cc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391342"
---
# <a name="configuring-cross-field-validation"></a>クロスフィールド検証の構成
このトピックでは、EDI でエンコードされたメッセージのトランザクション セット データ要素に対するクロスフィールド/セグメント検証を有効にする方法について説明します。 これを行うには、2 つの設定を行う必要があります。  
  
-   EDI スキーマの注釈にクロスフィールド検証フラグを設定します。 X12 または HIPAA スキーマでは、これは、 **X12ConditionDesignator_Check**フラグ。 EDIFACT スキーマの場合、これは、 **EdifactDependencyRule_Check**フラグ。  
  
-   アグリーメントのプロパティで EDI 型の検証を有効にします。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="configuring-cross-field-validation"></a>クロスフィールド検証の構成  
  
1. BizTalk エディターでスキーマを開きます。  
  
2. X12 または HIPAA スキーマ、検索、 **X12ConditionDesignator_Check**スキーマの appinfo セクションの注釈のフラグ。 設定**はい**します。  
  
   > [!NOTE]
   >  X12ConditionDesignator_Check フラグを設定して**はい**BizTalk スキーマ エディターから実行することはできません。 フラグを設定するには、メモ帳などのテキスト エディターで開いて編集し、スキーマ ファイル (.xsd) を保存する必要があります。  
  
3. EDIFACT スキーマで、検索、 **EdifactDependencyRule_Check**スキーマの appinfo セクションの注釈のフラグ。 設定**はい**します。  
  
4. スキーマの適切なセグメントに対して、適用する関係条件 (X12 および HIPAA) または依存ルール (EDIFACT) を指定します。 詳細については、次を参照してください。[クロス フィールド/セグメント検証](../core/cross-field-segment-validation.md)です。  
  
   > [!NOTE]
   >  クロスフィールド検証の条件またはルールは、EDI スキーマのセグメントに対して入力されます。 セグメントではなくデータ要素に対してクロスフィールド検証ルールを入力すると、スキーマ検証の実行時に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって警告が生成されます。  
  
5. **検証**ページ (で、**トランザクション セットの設定**セクション) の一方向アグリーメント タブの**アグリーメントのプロパティ**関連するアグリーメントは、ダイアログ ボックス必ず、 **EDI の種類の検証**プロパティが選択されています。  
  
## <a name="see-also"></a>参照  
 [EDI スキーマの開発](../core/developing-edi-schemas.md)