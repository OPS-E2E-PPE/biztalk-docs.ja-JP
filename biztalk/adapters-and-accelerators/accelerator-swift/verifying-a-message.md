---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cff0cb63f88bf2b69dc01862bf8257864c00d54
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529645"
---
# <a name="verifying-a-message"></a>メッセージの検証
このセクションでは、修復が完了するメッセージを確認する方法について説明します。  

### <a name="to-verify-a-message"></a>メッセージを確認するには  

1. Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。  

2. [ホーム] ウィンドウ**ドキュメント**します。  

3. ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>_Verifier**します。  

4. [確認] ウィンドウ**受信トレイ**します。  

5. 確認の受信トレイ ウィンドウで、メッセージのタイトルにポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。  

6. **ファイルのダウンロード**ダイアログ ボックスで、をクリックして**オープン**します。  

7. 現在のロール。RekeyVerify ウィンドウ、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**します。 示すように、エラーを確認、**解析と XML の検証エラー**ボックスおよび**BRE 検証エラー**ボックス。  

8. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認します。 クリックして、元のエラーがわかります**エラー**現在のロール。RekeyVerify ウィンドウで、およびエラー ウィンドウのいずれかでこのエラーを表示します。 クリックして、未修理、修正されたバージョンのメッセージを比較することもできます。**メッセージの詳細**、現在のロール。RekeyVerify ウィンドウです。  

9. メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール。RekeyVerify ウィンドウで、をクリックし、**検証メッセージ**。  

   > [!NOTE]
   >  [現在のロールでのメッセージの検証の結果ウィンドウ:RekeyVerify] ウィンドウでは、キーを再入力する必要のあるメッセージのすべてのフィールドを示します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 赤いアスタリスクが付けられてメッセージ ウィンドウでこれらのフィールドをマークします。  

10. (データを送信する前に変更する必要があることを示す) 赤いアスタリスクでマークされたメッセージのウィンドウですべてのフィールドにデータを再入力します。  

    > [!NOTE]
    >  クリックして、メッセージのフィールドにキーを再入力する必要があるデータを表示できる**メッセージの詳細**現在のロール。RekeyVerify ウィンドウとフィールドに、元のメッセージをスクロールします。 これは、元のメッセージ内のキーを再入力フィールドのいずれかで検証エラーが発生した場合を除き、true を再入力すると、フィールドを修復する必要がある場合。  

11. クリックして**検証**で、**現在のロール。RekeyVerify**ペイン、およびクリック**検証メッセージ**します。 結果ウィンドウが、メッセージが表示されることを確認 **、メッセージが有効な**します。  

12. クリックして**送信**で、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウ。  

    > [!NOTE]
    >  クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  

13. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで検証済みのメッセージを送信します。 をクリックして**拒否**拒否の変更で、メッセージを送信します。 クリックして**キャンセル**送信をキャンセルし、フォームに戻ります。  

    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
    > 
    > [!NOTE]
    >  メッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成するか修復) と修復のワークフローがリセットされます。  

14. デジタル署名のウィザード ページで、フォームに署名する証明書を選択するためには、フォーム (検証用に作成した書) の署名に使用する証明書を選択し をクリックし、**次**します。  

    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**. このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソール。  

15. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。  

16. デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。  

17. デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。  

18. [送信の成功] ダイアログ ボックスで、 **OK**します。  

19. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。  

20. サイトの MRSR クリックして**ドキュメントし、リスト**します。 クリックした場合は**Accept**手順 13 で変更を許可することを確認、\<部門名\>_Approve ドキュメント ライブラリが変更されただけのメッセージが含まれています。 ドキュメントとリストのウィンドウが開いて既にが存在する場合にクリックします**更新**上、**ビュー**メニュー。 クリックした場合は**拒否**手順 13 で変更を却下することを確認、 *\<コンピューター名\>*_Outbox ドキュメント ライブラリが変更されただけのメッセージが含まれています。
