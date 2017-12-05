---
title: "メッセージを承認する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3bdbd4845ddc1dff698274492f33ec69d659188
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="approving-a-message"></a>メッセージを承認します。
このセクションでは、修復および検証されているメッセージを承認する方法について説明します。  
  
### <a name="to-approve-a-message"></a>メッセージを承認するには  
  
1.  Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。  
  
2.  [ホーム] ウィンドウ**ドキュメント**です。  
  
3.  ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして  **\<*部門名*\>_Approver * *。  
  
4.  \<部門名\>_Approver ウィンドウで、をクリックして**受信トレイ**です。  
  
5.  受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックし、をクリックして**Microsoft Office InfoPath で編集**です。  
  
6.  SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**です。 示すようにエラーを確認、**解析と XML 検証エラー**ボックスで、 **BRE 妥当性確認エラー**ボックス、および**ランタイム エラー**ボックス。  
  
7.  [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認してください。 クリックして元のエラーを参照してください**エラー**現在のロールで: ペイン、およびエラー ペインのいずれかで、エラーの表示を承認します。 クリックして、メッセージのバージョンの未修理と修復されたバージョンを比較することもできます。**メッセージの詳細**、現在のロールで: ウィンドウを承認します。  
  
8.  メッセージを検証するためには、をクリックして**検証**、現在のロールで: ウィンドウを承認し、をクリックして**検証メッセージ**です。 結果ペインがメッセージを表示することを確認してください。**メッセージが有効では**します。  
  
9. ドキュメントに加えられた変更の承認した場合、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**です。  
  
    > [!NOTE]
    >  クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  
  
10. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れと共に、承認されたメッセージを送信するためです。 をクリックして**拒否**拒否変更と共に、メッセージを送信するためです。 をクリックして**キャンセル**送信をキャンセルし、フォームに戻る。  
  
    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
  
    > [!NOTE]
    >  メッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成または修復) し、修復ワークフローをリセットします。  
  
11. デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (証明書承認用に作成) の署名に使用する証明書を選択します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 **[次へ]**をクリックします。  
  
    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**. 表示できます (フォームのみ署名できるワークフローごとに 1 回のユーザーによって)、フォーム以前に署名するロールをクリックして**デジタル署名**上、**ツール**メニュー。 このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールです。  
  
12. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。  
  
13. デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。  
  
14. デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。  
  
15. [送信の成功] ダイアログ ボックスで、 **OK**です。  
  
16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。  
  
17. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、送信メッセージを受信し、設定したフォルダーを開きます。 フォルダーが承認されたメッセージが含まれていることを確認します。 メッセージをメッセージが修復されたことを確認するテキスト エディターで開きます。