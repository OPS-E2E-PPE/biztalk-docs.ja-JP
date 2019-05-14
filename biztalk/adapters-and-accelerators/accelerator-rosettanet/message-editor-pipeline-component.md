---
title: メッセージ エディタ パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b010f9f1e8a1217e2928ef4cfd147b56bf7043
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283211"
---
# <a name="message-editor-pipeline-component"></a>メッセージ エディタ パイプライン コンポーネント
このコンポーネントでは、受信パイプラインまたは送信内のマルチパート メッセージの一部を自動的に編集することができます。 このコンポーネントを通常の処理の一部として置換を設定する既存のパイプラインに追加します。  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a>メッセージ エディタ パイプライン コンポーネントを既存のパイプラインに組み込む  
 メッセージ エディタ パイプライン コンポーネントを使用するには、既存のパイプラインにコンポーネントを追加する必要があります。 詳細については、」を作成するパイプライン「パイプライン デザイナーで BizTalk Server のヘルプを参照してください。  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a>メッセージ エディタ パイプライン コンポーネントを既存のパイプラインに追加するには  
  
1. Visual Studio を起動します。  
  
2. **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。  
  
3. C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Editor Pipeline Component では、選択 **[messageeditor.csproj]**、順にクリックします**開く**.  
  
4. Visual Studio コマンド プロンプトを起動します。  
  
5. コマンド プロンプトで C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug します。  
  
6. コマンド プロンプトで「 **sn-k MessageEditor.snk**キーを作成し、ENTER キーを押します。  
  
7. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリックして **[messageeditor]**、 をクリックし、**プロパティ**します。  
  
8. **MessageEditor プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。  
  
9. **厳密な名前キー ファイルを選択して**ドロップダウンで、C:\Program Files (x86) \microsoft BizTalk\<バージョン\>アクセラレータを選択してください Editor Pipeline component \obj\debug**MessageEditor.snk**し**オープン**します。  
  
10. ソリューション エクスプ ローラーで右クリックして**messageeditor**、 をクリックし、**ビルド**します。 [出力] ウィンドウで、ビルドが成功したことを確認します。  
  
11. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。  
  
12. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーには、C:\Program files \microsoft BizTalk 2013 Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug の移動を右クリックして **[microsoft.solutions.btarn.sdk.messageeditor.dll]**、クリックして**コピー**します。  
  
13. 2013\Pipeline コンポーネントを C:\Program files \microsoft BizTalk Server に移動、右クリックして**パイプライン コンポーネント**、 をクリックし、**貼り付け**します。  
  
14. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**開く**、クリックして**プロジェクト**です。  
  
15. エディターを追加するパイプラインを含んでいるプロジェクトを開きます。  
  
16. ソリューション エクスプ ローラーでは、パイプライン デザイナーでパイプラインを開くパイプライン名をダブルクリックします。  
  
17. ツールボックス ウィンドウの BizTalk パイプライン コンポーネント ペインで右クリックし をクリックし、**アイテムの追加/削除**します。  
  
18. **ツールボックスのカスタマイズ** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **BTARN Message Editor Component**、順にクリックします**ok**.  
  
19. [ツールボックス] ウィンドウの [BizTalk パイプライン コンポーネント] ウィンドウで、クリックして押したまま**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。  
  
20. [ツールボックス] ウィンドウの [BizTalk パイプライン コンポーネント] ウィンドウで、クリックして押したまま**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。  
  
    > [!NOTE]
    >  メッセージ エディタ パイプライン コンポーネントは、逆アセンブル ステージでは、受信パイプライン コンポーネント、または送信パイプライン コンポーネントのプリアセンブル ステージの後に追加することをお勧めします。  
  
21. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、パイプライン デザイナーで、選択、 **BTARN Message Editor Component**図形。  
  
22. 関連付けられているテキスト ボックスに、プロパティ ペインで**XPath クエリ**値を変更する XPath 要素の名前を入力します。  
  
23. 関連付けられているテキスト ボックスに**XPath 値**、XPath 要素を設定する値を入力します。  
  
24. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。 ビルドが成功したことを確認します。  
  
25. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。 デプロイが成功したことを確認します。  
  
## <a name="example"></a>例  
 要素の値を変更する`ProprietaryDocumentIdentifier`0c1 で PIP スキーマでは、メッセージ エディタ パイプライン コンポーネントの XPath クエリ プロパティに次のコード セクションに示すように XPath クエリを追加します。  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 完全な XPath クエリを取得するスキーマを BizTalk エディターで開くしから Xpath をコピーし、`Instance XPath`プロパティ ウィンドウの下のプロパティ。 指定した XPath クエリでその名前空間のすべての参照が必要です。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
