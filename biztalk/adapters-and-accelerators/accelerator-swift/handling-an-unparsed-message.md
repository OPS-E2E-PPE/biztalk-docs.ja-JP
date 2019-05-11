---
title: 未解析メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77478326c3f2f457c5b88b4234d8087ec512215b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377501"
---
# <a name="handling-an-unparsed-message"></a>未解析メッセージの処理
このセクションでは、未解析のメッセージを処理する方法について説明します。 検証に失敗したメッセージとは異なり、メッセージを修復することはできませんを[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]を解析できません。 Message Repair and New Submission は、メッセージと、解析エラーの性質を表示し、メッセージを印刷したり、ローカル ファイルに保存することができます。 エンティティは解析エラーの特定の性質にメッセージを送信し、通知を送信できます。  

### <a name="to-handle-an-unparsed-message"></a>未解析メッセージを処理するには  

1. Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。  

2. [ホーム] ウィンドウ**ドキュメント**します。  

3. ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして**Unparsed**します。  

4. 未解析のウィンドウでは、次のようにクリックします。**受信トレイ**します。  

5. 未解析の受信トレイ] ウィンドウで、メッセージをポイントして、でしたいない解析、メッセージの右側にある矢印をクリックし、[ **Microsoft Office InfoPath で編集**します。  

6. SWIFT アクセラレータ ウィンドウで次のようにクリックします。**エラー**します。  

7. 解析と XML の検証エラー ウィンドウで、解析エラーを読み取ります。  

8. 未解析メッセージのウィンドウで、メッセージを確認します。  

   > [!NOTE]
   >  未解析メッセージのウィンドウで、メッセージを印刷する場合、**ファイル** メニューのをクリックして**印刷**します。  
   > 
   > [!NOTE]
   >  未解析メッセージのウィンドウで、ローカル ファイルにメッセージを保存する場合、**ファイル** メニューのをクリックして**名前を付けて保存**します。 **名前を付けて保存** ダイアログ ボックスで、**で保存**ドロップダウン リストをクリックして、ファイルを保存するフォルダーに移動**OK**します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] XML 形式でメッセージを保存します。  

9. 未解析メッセージのウィンドウで、必要に応じて変更し、**送信**します。  

    > [!NOTE]
    >  修復が未解析メッセージを検証することはできません。  

10. Submit Message ダイアログ ボックスで、 **Accept**を受け入れられる変更では修復されたメッセージを送信する をクリックして**拒否**、変更を拒否またはをクリックする**キャンセル**をキャンセルするには送信と、フォームに戻ります。  

11. クリックした場合は**Accept**または**拒否**デジタル署名ウィザード ページで、手順 11 では、フォーム (修理会社用に作成した書) の署名に使用する証明書を選択し、クリックして**次**します。  

    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.  

    > [!NOTE]
    >  任意のロールを実行するすべてのユーザーには、それを修復が未解析のメッセージを送信できます。  

12. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。  

13. デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。  

14. デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。  

15. [送信の成功] ダイアログ ボックスで、 **OK**します。  

16. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。
