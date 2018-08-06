---
title: メッセージの修復 |Microsoft Docs
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9edb8f9cc3c5db67e75ff47125e0d58891a5173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992043"
---
# <a name="repairing-a-message"></a>メッセージの修復
このセクションでは、検証が失敗したメッセージを修復する方法について説明します。  

### <a name="to-repair-a-message"></a>メッセージを修復するには  

1. Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。  

2. [ホーム] ウィンドウ**ドキュメント**します。  

3. ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>**_**修理会社**.  

4. \<*部門名*\>_Repair ウィンドウで、をクリックして**受信トレイ**します。  

5. 受信トレイ ウィンドウで、メッセージのタイトルをポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。  

6. SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、いることを確認**エラー**が選択されています。 示すように、エラーを確認、**解析と XML の検証エラー**、 **BRE 検証エラー**、および**ランタイム エラー**ボックス。  

7. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、エラーの場所にスクロールし、エラーを修正します。 XML 検証エラーは、エラーは赤で強調表示されます。  

   > [!NOTE]
   >  BRE の検証エラーが赤で強調表示されませんが、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 BRE の検証エラーに関する詳細については、次を参照してください。 [SWIFT エラー コード](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)します。  
   > 
   > [!NOTE]
   >  ドロップダウン リストでは、関連付けられているフィールドに、エラーが発生した場合、エラーの原因となった元の値を表示することができなきます。 フィールドが表示されます"Select"元の値の代わりにします。 ドロップダウン リストから適切な値を選択します。  

8. メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール: ウィンドウを修復し、順にクリックします**検証メッセージ**します。 結果ペインが表示されることを確認 **、メッセージが有効な**します。  

9. [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**します。  

   > [!NOTE]
   >  クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。 検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。  

10. Submit Message ダイアログ ボックスで、 **Accept**を受け入れられる変更では修復されたメッセージを送信する をクリックして**拒否**、変更を拒否またはをクリックする**キャンセル**をキャンセルするには送信と、フォームに戻ります。  

    > [!NOTE]
    >  メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。  
    > 
    > [!NOTE]
    >  修復段階でメッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを MessageBox にルーティングし、イベント ビューアーを読み取るエラーへの投稿「をリセットできませんでした、ワークフローの最初のステージを。」です。  

11. クリックした場合**Accept**または**拒否**に手順 10 で、**デジタル署名ウィザード**ページで、フォームの署名に使用する証明書を選択します (証明書を用に作成、修理会社)、順にクリックします**次**します。  

    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.  

12. デジタル署名のウィザード ページで、コメントを入力するためには、をクリックして**完了**します。  

13. デジタル署名ウィザード ページで、フォームを検証するため、メッセージに署名して、署名が正しいことを確認します。 クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。  

14. デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。  

15. [送信の成功] ダイアログ ボックスで、 **OK**します。  

16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。  

17. サイトの MRSR クリックして**ドキュメント**します。 クリックした場合**Accept**手順 11 で変更を許可することを確認、 *\<部門名\>*_ReKeyVerify ドキュメント ライブラリには、修復したメッセージが含まれています。 クリックした場合は**拒否**手順 11 で変更を却下する A4SWIFT_Outbox ドキュメント ライブラリに変更されたメッセージが含まれていることを確認します。
