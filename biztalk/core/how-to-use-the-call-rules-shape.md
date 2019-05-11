---
title: ルール図形の呼び出しを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9cf784eba26f93e6634863d02d36a4bb2e01c38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333258"
---
# <a name="how-to-use-the-call-rules-shape"></a>ルールの呼び出し図形を使用する方法
オーケストレーション デザイナーで使用することができます、**ルールの呼び出し**図形を呼び出すビジネス ポリシー。  
  
### <a name="to-configure-the-call-rules-shape"></a>ルールの呼び出し図形を構成するには  
  
1. ツールボックスで、 **BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面上の区分線にします。  
  
    - または -  
  
    区分線または図形を追加する図形のプレース ホルダーを右クリックして をポイント**図形の挿入** をクリックし、コンテキスト メニューで**ルールの呼び出し**します。  
  
   > [!NOTE]
   >  BizTalk Server では挿入するアトミックのスコープを持つ必要はありません、**ルールの呼び出し**図形。 ドラッグすることができます、**ルールの呼び出し**図形をツールボックスからオーケストレーション デザイン画面にします。 ただし、BizTalk Server で、**ルールの呼び出し**を挿入しようとする場合、コンテキスト メニューにメニュー項目が無効です、**ルールの呼び出し**アトミックのスコープを持たないオーケストレーション内の図形。 これは、使用制限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品です。  
  
2. オーケストレーション デザイナーで、選択、**ルールの呼び出し**図形。  
  
3. 表示する図形をダブルクリックして、 **CallRules ポリシーの構成** ダイアログ ボックス。  
  
4. **呼び出すビジネス ポリシーの選択**ドロップダウン リストで、必要なポリシーを選択します。  
  
   > [!NOTE]
   >  ポリシーで使用される型を決定するときに、ポリシーの保存されている最新のバージョンの呼び出し規則の構成になります。 実行時に、ポリシーの展開された最新のバージョンが使用します。  
  
5. **ポリシー パラメーターの指定**リスト ボックスから変数を選択して、**パラメーター名**プロパティ。  
  
   > [!NOTE]
   >  **ルールの呼び出し**図形は基本的に再構築する際、メッセージを使用した場合、**構築**図形、失われたメッセージのコンテキスト プロパティがさらに可能性があります。  
  
   > [!NOTE]
   >  BRE ポリシーのパラメーターとしては、メッセージまたは .NET 変数を指定できます。 渡す、 **TypedXmlDocument**実際には、パラメーターとしてオーケストレーションで宣言されている対応するメッセージを指定します。 .NET ファクトを渡すには、パラメーターとしてオーケストレーションで宣言されている .NET 変数を指定します。 型の .NET 変数を指定すると、データベース ファクトを渡すため**DataConnection**または**TypedDataTable**ポリシーへのパラメーターとして。