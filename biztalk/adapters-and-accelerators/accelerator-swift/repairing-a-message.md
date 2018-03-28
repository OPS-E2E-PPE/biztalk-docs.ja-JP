---
title: メッセージの修復 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4489e463257f811fe2c71efea49880940751c66a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="repairing-a-message"></a>メッセージの修復
このセクションでは、検証が失敗したメッセージを修復する方法について説明します。  
  
### <a name="to-repair-a-message"></a>メッセージを修復するには  
  
1.  Internet Explorer で、開くで MRSR サイトhttp://localhost/sites/bassiteです。  
  
2.  [ホーム] ウィンドウ**ドキュメント**です。  
  
3.  ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして **\<*部門名*\>**_**修理会社**.  
  
4.  \<*部門名*\>_Repair ウィンドウで、をクリックして**受信トレイ**です。  
  
5.  受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックし、をクリックして**Microsoft Office InfoPath で編集**です。  
  
6.  SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、いることを確認**エラー**が選択されています。 示すように、エラーを確認して、**解析と XML 検証エラー**、 **BRE 妥当性確認エラー**、および**ランタイム エラー**ボックス。  
  
7.  [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの場所にスクロールし、エラーを修正します。 XML 検証エラーがある場合、エラーは赤色で強調表示されます。  
  
    > [!NOTE]
    >  BRE の妥当性確認エラーが赤色で強調表示されませんが、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 BRE の検証エラーの詳細については、次を参照してください。 [SWIFT エラーコード](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)です。  
  
    > [!NOTE]
    >  ドロップダウン リストが関連付けられているフィールドにエラーが発生する場合、エラーの原因となった元の値を表示することができなきます。 フィールドが表示されます"Select"元の値の代わりにします。 ドロップダウン リストから適切な値を選択します。  
  
8.  メッセージを検証するためには、をクリックして**検証**、現在のロールで: ウィンドウを修復し、をクリックして**検証メッセージ**です。 結果ペインが表示されることを確認**メッセージが有効では**します。  
  
9. [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**です。  
  
    > [!NOTE]
    >  クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  
  
10. [Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで修復されたメッセージを送信するには、クリックして**拒否**をクリックする、変更を拒否するか**キャンセル**をキャンセルするには送信と、フォームに戻る。  
  
    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
  
    > [!NOTE]
    >  修復段階でメッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを MessageBox にルーティングし、イベント ビューアーを読み取るエラーへのポスト「でしたにリセットしないワークフローの最初のステージ。」です。  
  
11. クリックした場合は**Accept**または**拒否**手順 10 では、上、**デジタル署名ウィザード** ページで、フォームの署名に使用する証明書を選択 (証明書を修理会社用) を作成し、をクリックして**次**です。  
  
    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.  
  
12. デジタル署名のウィザード ページで、コメントを入力するためには、をクリックして**完了**です。  
  
13. デジタル署名ウィザードのページで、フォームを検証するため、メッセージ署名して、署名が正しいことを確認します。 をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。  
  
14. デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。  
  
15. [送信の成功] ダイアログ ボックスで、 **OK**です。  
  
16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。  
  
17. サイトの MRSR クリックして**ドキュメント**です。 クリックした場合は**Accept**手順 11 で変更を受け入れるようにいることを確認、 *\<部門名\>*_ReKeyVerify ドキュメント ライブラリには、修復するメッセージが含まれています。 クリックした場合は**拒否**手順 11 で変更を拒否する A4SWIFT_Outbox ドキュメント ライブラリに変更が、メッセージが含まれていることを確認します。