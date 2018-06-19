---
title: 作成して、新しいメッセージを送信する |Microsoft ドキュメント
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
ms.openlocfilehash: 42cd2a82fe0ecde75446e68f9f58e17f103e5efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209866"
---
# <a name="creating-and-submitting-a-new-message"></a>作成して、新しいメッセージを送信します。
このセクションでは、新しいメッセージを送信する方法について説明します。 として修復されたメッセージを表示して、新しいメッセージ必要がある確認および承認されたメッセージの作成者は、他のユーザーによってです。  
  
 新しいメッセージを送信するには、必要があります、新しい SWIFT メッセージ ドキュメント ライブラリに、メッセージ テンプレート ファイルをアップロードする送信するメッセージの種類。 1 つのメッセージ テンプレートを手動でアップロードすることができますか FormPublish ツールを使用してすべてのメッセージのテンプレートをアップロードすることができます。  
  
### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a>新しいドキュメント ライブラリに 1 つのメッセージのテンプレートをアップロードするには  
  
1.  セクションを参照してください[フォーム ジェネレーター ユーティリティ MT/MX InfoPath フォームの生成に](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)手順についてはします。  
  
### <a name="to-create-and-submit-a-new-message"></a>作成して、新しいメッセージを送信するには  
  
1.  Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。  
  
2.  をクリックして**ドキュメント**、クリックして**新しい SWIFT メッセージ**です。  
  
3.  新しい SWIFT メッセージ ページで、作成するには、メッセージの種類を表すカテゴリの名前をダブルクリックします。  
  
4.  作成するメッセージのフォーム テンプレートをクリックします。  
  
5.  [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年 ウィンドウのメッセージで、フォームの型メッセージとデータをすべての必須フィールド (アスタリスクで表します) として使用する省略可能なフィールドです。  
  
6.  現在の役割で、BIC を検索する: ウィンドウの作成 をクリックして**BIC 参照**です。  
  
7.  金融機関、銀行コードと国/地域の名前を入力し、クリックして**検索**です。  
  
8.  BIC 参照ペインからは、メッセージ形式で、適切な銀行コード フィールドに、BIC をコピーします。  
  
9. 現在のロールで: ウィンドウの作成 をクリックして**検証**、順にクリック**検証メッセージ**です。  
  
10. 結果ウィンドウで、現在のロールの: ウィンドウを作成、メッセージを修正する必要のあるエラーを確認します。  
  
    > [!NOTE]
    >  メッセージのすべての検証エラーを修正した場合にのみ、新しいメッセージを送信できます。  
  
11. ウィンドウの上部にある [標準] ツールバーからをクリックして**送信**です。  
  
12. デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (証明書の作成者は、作成した) の署名に使用する証明書を選択します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 **[次へ]** をクリックします。  
  
    > [!NOTE]
    >  デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.  
  
13. デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。  
  
14. デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。 をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。 をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。  
  
15. デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。  
  
16. [送信の成功] ダイアログ ボックスで、 **OK**です。  
  
17. 閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。