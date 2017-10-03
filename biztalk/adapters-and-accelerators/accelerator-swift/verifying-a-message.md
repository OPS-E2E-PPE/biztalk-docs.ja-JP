---
title: "メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e22d5c24b0c2d29c225fa2206d47b67e3d166a2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-a-message"></a>メッセージの検証
このセクションでは、修復されましたが、メッセージを確認する方法について説明します。  
  
### <a name="to-verify-a-message"></a>メッセージを確認するには  
  
1.  Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。  
  
2.  [ホーム] ウィンドウ**ドキュメント**です。  
  
3.  ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして  **\<*部門名*> _Verifier * *。  
  
4.  確認してください ウィンドウで、をクリックして**受信トレイ**です。  
  
5.  確認の受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックして**Microsoft Office InfoPath で編集**です。  
  
6.  **ファイルのダウンロード**ダイアログ ボックスで、をクリックして**開く**です。  
  
7.  現在のロールで: RekeyVerify ウィンドウの[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**です。 示すように、エラーを確認して、**解析と XML 検証エラー**ボックスおよび**BRE 妥当性確認エラー**ボックス。  
  
8.  [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認してください。 クリックして元のエラーを参照してください**エラー**現在のロールで: RekeyVerify ウィンドウで、エラー ウィンドウのいずれかでエラーを表示するとします。 クリックして、メッセージのバージョンの未修理と修復されたバージョンを比較することもできます。**メッセージの詳細**で、現在のロール: RekeyVerify ウィンドウです。  
  
9. メッセージを検証するためには、をクリックして**検証**、現在のロールで: RekeyVerify ウィンドウで、をクリックして**検証メッセージ**です。  
  
    > [!NOTE]
    >  現在のロールでのメッセージの検証 [結果] ペイン: RekeyVerify ウィンドウは、キー更新する必要のあるメッセージのすべてのフィールドを示します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]赤いアスタリスクの付いたメッセージ ウィンドウでこれらのフィールドをマークします。  
  
10. ウィンドウで、メッセージ (送信の前に、データを再生成する必要があることを示す)、赤いアスタリスクでマークされたすべてのフィールドにデータを鍵更新します。  
  
    > [!NOTE]
    >  メッセージ フィールドにキーを更新する必要のあるデータを表示する をクリックして**メッセージの詳細**現在のロールで: RekeyVerify ウィンドウで、フィールドに、元のメッセージのスクロールとします。 これは、元のメッセージ内のキー更新フィールドのいずれかで検証エラーが発生した場合を除き、true に鍵を更新するときに、フィールドを修復する必要場合。  
  
11. をクリックして**検証**で、**現在のロール: RekeyVerify**  ウィンドウで、クリックして**検証メッセージ**です。 結果ペインがメッセージを表示することを確認してください。**メッセージが有効では**します。  
  
12. をクリックして**送信**で、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウです。  
  
    > [!NOTE]
    >  クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  
  
13. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れと共に確認済みのメッセージを送信するためです。 をクリックして**拒否**拒否変更と共に、メッセージを送信するためです。 をクリックして**キャンセル**送信をキャンセルし、フォームに戻る。  
  
    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
  
    > [!NOTE]
    >  メッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成または修復) し、修復ワークフローをリセットします。  
  
14. デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (、証明書を検証用に作成した)、署名に使用する証明書を選択し、をクリックして**次**です。  
  
    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**. このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールです。  
  
15. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。  
  
16. デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。  
  
17. デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。  
  
18. [送信の成功] ダイアログ ボックスで、 **OK**です。  
  
19. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。  
  
20. サイトの MRSR クリックして**ドキュメントし、リスト**です。 クリックした場合は**Accept**手順 13. の変更を受け入れるようにいることを確認、\<部門名 > _Approve ドキュメント ライブラリには、直前に変更するメッセージが含まれています。 開いているドキュメントとリストのウィンドウが既に存在する場合はクリックして**更新**上、**ビュー**メニュー。 クリックした場合は**拒否**手順 13. の変更を拒否することを確認、 *\<コンピューター名 >*_Outbox ドキュメント ライブラリには、直前に変更するメッセージが含まれています。