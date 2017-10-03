---
title: "スキーマの種類から Web メッセージ部分を構築する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3434dc46be2fa43885346ac8d146e9326ab1ea73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a>スキーマの種類から Web メッセージ部分を構築する方法
使用してスキーマの種類から Web メッセージ部分を作成する、**変換**図形です。 または、Web メッセージ部分を設定する .NET ヘルパー クラスを使用して、スキーマの種類から Web メッセージ部分を作成することもできます。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a>スキーマの種類から Web メッセージ部分を構築するには  
  
1.  新しいマップを追加します。 マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)です。  
  
2.  BizTalk マッパーでクリックして**送信先スキーマを開く**で、**送信先スキーマ**ペインのマップし、[、 **BizTalk 型の選択**] ダイアログ ボックスで、展開、 **スキーマ**ノード、追加の Web 参照スキーマを選択し、をクリックして**OK**です。  
  
    > [!NOTE]
    >  Web 参照スキーマの形式が**\<プロジェクトの既定の名前空間 >.\<Web 参照名 >。参照**です。  
  
3.  **ターゲット スキーマのルート ノード**ダイアログ ボックスでは、送信先スキーマのルート ノードを選択し、をクリックして**OK**です。 Web メッセージ部分の型のルート ノードを確認する方法の詳細については、次を参照してください。 [Web メッセージ部分の型を確認する方法](../core/how-to-determine-a-web-message-part-type.md)です。  
  
4.  をクリックして**ソース スキーマを開く**で、**送信元スキーマ**ペインのマップし、[、 **BizTalk 型の選択**] ダイアログ ボックスで、展開、**スキーマ**ノードで、データをマップの送信元スキーマを選択してをクリック**OK**です。  
  
5.  BizTalk マッパーで、送信元スキーマと送信先スキーマの間のリンクを作成します。  
  
6.  既存のオーケストレーションを開きます (または、新しいオーケストレーションを作成)、開く、**ツールボックス**、 をクリックし、 **BizTalk オーケストレーション** タブ。  
  
7.  ドラッグ、**メッセージの構築**オーケストレーションへの図形です。  
  
8.  編集、**メッセージ構築**Web メッセージの種類用に作成したメッセージを含めるプロパティをインスタンスします。  
  
9. ドラッグ、**変換**図形の上に、**メッセージの構築**図形しをダブルクリックして開きます、**変換の構成** ダイアログ ボックス。  
  
10. クリックして、**既存のマップ**ボタンをクリックし、手順 1 で作成したマップを選択、**完全修飾マップ名**ボックスの一覧です。  
  
11. **変換**ペインで、**ソース**です。 **送信元の変換**ペインで、有効なメッセージが、リスト ボックスからインスタンスを選択します。  
  
12. **変換**ペインで、**先**です。 **送信先の変換** ウィンドウで、Web メッセージ インスタンスのリスト ボックスからをクリックして**OK**です。  
  
 使用しての詳細については、**変換の構成**ダイアログ ボックスを参照してください[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md)です。  
  
 この手順を使用して、Web メソッドの応答メッセージ インスタンスを別の Web メッセージ インスタンスにマップすることもできます。  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)