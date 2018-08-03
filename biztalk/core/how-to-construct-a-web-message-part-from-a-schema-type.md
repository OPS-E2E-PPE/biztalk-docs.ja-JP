---
title: スキーマの種類から Web メッセージ部分を構築する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8fd01e67309387749e7e512eca84bdb0f83db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984795"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a>スキーマの種類から Web メッセージ部分を構築する方法
使用して、スキーマの種類から Web メッセージ部分を作成、**変換**図形。 または、Web メッセージ部分を設定する .NET ヘルパー クラスを使用して、スキーマの種類から Web メッセージ部分を作成することもできます。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a>スキーマの種類から Web メッセージ部分を構築するには  
  
1. 新しいマップを追加します。 マップを作成する方法の詳細については、次を参照してください。[新しいマップを作成する方法](../core/how-to-create-new-maps.md)します。  
  
2. BizTalk マッパーでは、クリックして**送信先スキーマを開く**で、**送信先スキーマ**ペインのマップし、 **BizTalk 型の選択** ダイアログ ボックスで、展開、 **スキーマ**ノードが Web 参照の追加のスキーマを選択し、クリックして**OK**します。  
  
   > [!NOTE]
   >  Web 参照スキーマの形式が**\<プロジェクトの既定の名前空間\>.\<Web 参照名\>します。参照**します。  
  
3. **ターゲット スキーマのルート ノード** ダイアログ ボックスで、送信先スキーマのルート ノードを選択し、順にクリックします**OK**します。 Web メッセージ部分の型のルート ノードを確認する方法の詳細については、次を参照してください。 [Web メッセージ部分の型を確認する方法](../core/how-to-determine-a-web-message-part-type.md)します。  
  
4. をクリックして**ソース スキーマを開く**で、**送信元スキーマ**ペインのマップし、 **BizTalk 型の選択** ダイアログ ボックスで、展開、**スキーマ**ノードからのデータをマップするソース スキーマを選択およびクリック**OK**します。  
  
5. BizTalk マッパーで、送信元スキーマと送信先スキーマの間のリンクを作成します。  
  
6. 既存のオーケストレーションを開きます (または、新しいオーケストレーションを作成) を開く、**ツールボックス**、 をクリックし、 **BizTalk オーケストレーション**タブ。  
  
7. ドラッグ、**メッセージの構築**オーケストレーションへの図形。  
  
8. 編集、**メッセージ構築**Web メッセージの種類用に作成したメッセージを含めるプロパティをインスタンスします。  
  
9. ドラッグ、**変換**図形の上に、**メッセージの構築**図形しをダブルクリックして開きます、**変換の構成** ダイアログ ボックス。  
  
10. をクリックして、**既存のマップ**ボタンをクリックし、手順 1 で作成したマップを選択、**完全修飾マップ名**ボックスの一覧。  
  
11. **変換**ペインで、**ソース**します。 **送信元の変換**ウィンドウで、有効なメッセージが、リスト ボックスからインスタンスを選択します。  
  
12. **変換**ペインで、**先**します。 **送信先の変換**ウィンドウで、Web メッセージ インスタンスをリスト ボックスから、クリックして選択**OK**します。  
  
    使用しての詳細については、**変換の構成**ダイアログ ボックスを参照してください[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md)します。  
  
    この手順を使用して、Web メソッドの応答メッセージ インスタンスを別の Web メッセージ インスタンスにマップすることもできます。  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)