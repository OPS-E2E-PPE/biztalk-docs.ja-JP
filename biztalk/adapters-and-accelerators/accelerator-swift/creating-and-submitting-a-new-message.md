---
title: 作成し、新しいメッセージの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5597788d20ad1f1e75b35a81ea7294de75830662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378475"
---
# <a name="creating-and-submitting-a-new-message"></a>作成して、新しいメッセージを送信します。
このセクションでは、新しいメッセージを送信する方法について説明します。 として修復されたメッセージを表示して、新しいメッセージをする必要がありますは、確認し、メッセージの作成者は、他のユーザーによって承認します。  

 新しいメッセージを送信するには、必要がありますアップロードする新しい SWIFT メッセージ ドキュメント ライブラリにメッセージを送信するメッセージの種類のテンプレート ファイル。 手動で 1 つのメッセージ テンプレートをアップロードするか、FormPublish ツールを使用してすべてのメッセージ テンプレートをアップロードすることができます。  

### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a>新しいドキュメント ライブラリに 1 つのメッセージ テンプレートをアップロードするには  

1.  セクションを参照してください[フォーム ジェネレーター ユーティリティ MT/MX InfoPath フォームを生成する](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)手順についてはします。  

### <a name="to-create-and-submit-a-new-message"></a>作成して、新しいメッセージを送信するには  

1. Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。  

2. をクリックして**ドキュメント**、 をクリックし、**新しい SWIFT メッセージ**します。  

3. 新しい SWIFT メッセージ ページで、作成するにはメッセージの種類を含むカテゴリの名前をダブルクリックします。  

4. フォームのテンプレートを作成するメッセージをクリックします。  

5. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年 ウィンドウのメッセージで、フォームの (アスタリスク書きます) として必要なすべてのフィールドを使用する省略可能なフィールドの種類のメッセージ データ。  

6. 現在のロールで、BIC: 検索するにはウィンドウの作成 をクリックして**BIC 参照**します。  

7. 金融機関、銀行コード、および国/地域の名前を入力し、クリックして**検索**します。  

8. BIC 参照ペインで、メッセージの形式で、適切な銀行コード フィールドに、BIC をコピーします。  

9. 内の現在の役割。ウィンドウの作成 をクリックして**検証**、 をクリックし、**検証メッセージ**します。  

10. 現在のロールの [結果] ウィンドウで。メッセージを修正する必要があるエラーを確認する、ウィンドウを作成します。  

    > [!NOTE]
    >  メッセージのすべての検証エラーを修正した場合にのみ、新しいメッセージを送信できます。  

11. ウィンドウの上部にある [標準] ツールバーからをクリックして**送信**します。  

12. デジタル署名ウィザード ページで、フォームに署名する証明書を選択するため、フォーム (作成者用に作成した書) の署名に使用する証明書を選択します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 **[次へ]** をクリックします。  

    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.  

13. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。  

14. デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。 クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。 クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。  

15. デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。  

16. [送信の成功] ダイアログ ボックスで、 **OK**します。  

17. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。
