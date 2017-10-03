---
title: "未解析のメッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b7683a598169b8ece75788584e8bb9b3c7f4861
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-an-unparsed-message"></a>未解析のメッセージの処理
このセクションでは、未解析のメッセージを処理する方法について説明します。 検証に失敗したメッセージとは異なり、メッセージを修復することはできませんを[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]を解析できません。 Message Repair and New Submission メッセージと、解析エラーの性質が表示され、メッセージを印刷またはローカル ファイルに保存することができます。 解析エラーの特定の性質にメッセージを送信するエンティティ、通知を送信できます。  
  
### <a name="to-handle-an-unparsed-message"></a>未解析のメッセージを処理するには  
  
1.  Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。  
  
2.  [ホーム] ウィンドウ**ドキュメント**です。  
  
3.  ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして**Unparsed**です。  
  
4.  未解析のウィンドウで **受信トレイ**です。  
  
5.  未解析の受信トレイ ウィンドウで、でしたいない解析、メッセージの右側にある矢印をクリックし、メッセージ をポイント**Microsoft Office InfoPath で編集**です。  
  
6.  SWIFT アクセラレータ ウィンドウで **エラー**です。  
  
7.  解析と XML 検証エラー ウィンドウでは、解析エラーを読み取る。  
  
8.  未解析のメッセージ ウィンドウで、メッセージを確認します。  
  
    > [!NOTE]
    >  Unparsed メッセージ ウィンドウで、メッセージを印刷する場合、**ファイル** メニューのをクリックして**印刷**です。  
  
    > [!NOTE]
    >  [Unparsed メッセージ ウィンドウで、ローカル ファイルにメッセージを保存する場合、**ファイル**] メニューのをクリックして**名前を付けて保存**です。 **名前を付けて保存** ダイアログ ボックスで、**で保存**、ドロップダウン リストで、ファイルを保存し、をクリックするフォルダーに移動**ok**です。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]XML 形式でメッセージを保存します。  
  
9. 未解析のメッセージ ウィンドウで、必要な変更を行いをクリックして**送信**です。  
  
    > [!NOTE]
    >  修復される未解析のメッセージを検証することはできません。  
  
10. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで修復されたメッセージを送信するには、クリックして**拒否**をクリックする、変更を拒否するか**キャンセル**をキャンセルするには送信と、フォームに戻る。  
  
11. クリックした場合は**Accept**または**拒否**デジタル署名ウィザード ページで、手順 11、フォーム (修理会社用に作成した書) の署名に使用する証明書を選択し、をクリックして**次**です。  
  
    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.  
  
    > [!NOTE]
    >  任意のロールを実行するすべてのユーザーには、修復、未解析のメッセージを送信できます。  
  
12. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。  
  
13. デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。  
  
14. デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。  
  
15. [送信の成功] ダイアログ ボックスで、 **OK**です。  
  
16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。