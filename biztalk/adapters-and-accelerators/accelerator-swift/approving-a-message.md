---
title: メッセージの承認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c565f40c6c455456101521414edf0c377411014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967107"
---
# <a name="approving-a-message"></a>メッセージの承認
このセクションでは、修復され検証されたメッセージを承認する方法について説明します。  

### <a name="to-approve-a-message"></a>メッセージを承認するには  

1. Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。  

2. [ホーム] ウィンドウ**ドキュメント**します。  

3. ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>_Approver**します。  

4. \<部門名\>_Approver ウィンドウで、をクリックして**受信トレイ**します。  

5. 受信トレイ ウィンドウで、メッセージのタイトルをポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。  

6. SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**します。 示すように、エラーを確認、**解析と XML の検証エラー**ボックスで、 **BRE 検証エラー**ボックスで、および**ランタイム エラー**ボックス。  

7. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認します。 クリックして、元のエラーがわかります**エラー**現在のロール: ペイン、およびエラー ウィンドウのいずれかで、エラーの表示を承認します。 クリックして、未修理、修正されたバージョンのメッセージを比較することもできます。**メッセージの詳細**、現在のロール: ウィンドウを承認します。  

8. メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール: 承認ウィンドウで、をクリック**検証メッセージ**します。 結果ウィンドウが、メッセージが表示されることを確認 **、メッセージが有効な**します。  

9. ドキュメントに加えられた変更を承認する場合、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**します。  

   > [!NOTE]
   >  クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  

10. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで承認されたメッセージを送信します。 をクリックして**拒否**拒否の変更で、メッセージを送信します。 クリックして**キャンセル**送信をキャンセルし、フォームに戻ります。  

    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
    > 
    > [!NOTE]
    >  メッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成するか修復) と修復のワークフローがリセットされます。  

11. デジタル署名ウィザード ページで、フォームに署名する証明書を選択するため、フォーム (承認者用に作成した書) の署名に使用する証明書を選択します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 **[次へ]** をクリックします。  

    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**. 確認できます (フォームのみ署名できるワークフローごとに 1 回のユーザーによって)、フォーム以前の済みであるロールをクリックして**デジタル署名**上、**ツール**メニュー。 このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソール。  

12. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。  

13. デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。  

14. デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。  

15. [送信の成功] ダイアログ ボックスで、 **OK**します。  

16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。  

17. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、送信されたメッセージを受信するように設定するフォルダーを開きます。 フォルダーが承認済みのメッセージが含まれていることを確認します。 メッセージをメッセージが修復されたことを確認するテキスト エディターで開きます。
