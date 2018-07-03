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
ms.openlocfilehash: 6955acfee9052a3b46dcfb70c90ecc95fe216be3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003115"
---
# <a name="how-to-use-the-call-rules-shape"></a>ルールの呼び出し図形の使用方法
オーケストレーション デザイナーで使用することができます、**ルールの呼び出し**図形を呼び出すビジネス ポリシー。  
  
### <a name="to-configure-the-call-rules-shape"></a>ルールの呼び出し図形を構成するには  
  
1. ツールボックスで、 **BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面上の区分線にします。  
  
    - または -  
  
    区分線または図形を追加する図形のプレース ホルダーを右クリックして をポイント**図形の挿入** をクリックし、コンテキスト メニューで**ルールの呼び出し**します。  
  
   > [!NOTE]
   >  BizTalk Server では挿入するアトミックのスコープを持つ必要はありません、**ルールの呼び出し**図形。 ドラッグすることができます、**ルールの呼び出し**図形をツールボックスからオーケストレーション デザイン画面にします。 ただし、BizTalk Server で、**ルールの呼び出し**を挿入しようとする場合、コンテキスト メニューにメニュー項目が無効です、**ルールの呼び出し**アトミックのスコープを持たないオーケストレーション内の図形。 これは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 製品における制限事項です。  
  
2. オーケストレーション デザイナーで、選択、**ルールの呼び出し**図形。  
  
3. 表示する図形をダブルクリックして、 **CallRules ポリシーの構成** ダイアログ ボックス。  
  
4. **呼び出すビジネス ポリシーの選択**ドロップダウン リストで、必要なポリシーを選択します。  
  
   > [!NOTE]
   >  ルールの呼び出しの構成は、ポリシーで使用される種類を決定する際、保存されている最新バージョンのポリシーを参照します。 実行時に、展開されている最新バージョンのポリシーが使用されます。  
  
5. **ポリシー パラメーターの指定**リスト ボックスから変数を選択して、**パラメーター名**プロパティ。  
  
   > [!NOTE]
   >  **ルールの呼び出し**図形は基本的に再構築する際、メッセージを使用した場合、**構築**図形、失われたメッセージのコンテキスト プロパティがさらに可能性があります。  
  
   > [!NOTE]
   >  BRE ポリシーのパラメーターとしては、メッセージまたは .NET 変数を指定できます。 渡す、 **TypedXmlDocument**実際には、パラメーターとしてオーケストレーションで宣言されている対応するメッセージを指定します。 .NET ファクトを渡すには、オーケストレーション内でパラメーターとして宣言済みの .NET 変数を指定します。 型の .NET 変数を指定すると、データベース ファクトを渡すため**DataConnection**または**TypedDataTable**ポリシーへのパラメーターとして。