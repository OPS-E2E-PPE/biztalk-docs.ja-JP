---
title: 生成して、SharePoint サイトで MT MX フォームの発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492eda3b4bf3d3950c084bc9234b52b911b84a2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980051"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>生成して、SharePoint サイトで MT/MX フォームの発行
**生成し、SharePoint サイトで MT/MX フォームを公開します。**  

1. フォーム ジェネレーター ユーティリティをダウンロードし、ローカル コンピューターに保存します。  

2. 開く、 **FormGenerator.sln**上記でダウンロードしたフォルダーから、ソリューションをコンパイルします。  

3. コマンド プロンプトでコンパイルされた実行可能ファイル (FormGenerator.exe) のフォルダーにアクセスします。 たとえば、デバッグ モードでユーティリティをビルドした場合にアクセス、 **.\bin\debug**フォルダー。  

4. 入力 FormGenerator.exe [-b] [-\<いいえ。 テンプレート フォルダーのパスの\>]  

    `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`。 パラメーターを新しく作成したフォルダーの名前に置き換えます。  

5. 上記のコマンドでは、MX メッセージの修復に必要なエンベロープ スキーマも生成されます。  

6. 出力フォルダーに移動して\<DestinationFolderPath\>します。 \<DestinationFolderPath\>フォームを生成する InfoPath フォーム テンプレートのフォルダーを開きます。 たとえば、MT103 InfoPath フォームを生成する場合は、DestinationFolderPath MT103 フォルダーを開くし、TemplateDS.sln を開きます。  

7. ソリューション エクスプ ローラーで、ダブルクリック、 **manifest.xsf**します。 取得に開かれる時間のかかるが InfoPath フォームのデザインのファイルが開きます。  

   > [!NOTE]
   >  MX メッセージの manifest.xsf は開く取得 2 ~ 5 分かかります。  

8. Manifest.xsf に移動**ツール、オプション フォーム - > セキュリティと信頼**メニュー オプション。 チェック、**完全信頼**アクセス許可のオプションを有効にする必要があります。  

9. 選択、**このフォーム テンプレートの署名**チェック ボックスをオンします。 クリックして**証明書の選択**します。 これには、フォームに署名する証明書を選択します。 **[OK]** をクリックします。  

10. 保存**manifest.xsf**します。  

11. 移動して**ビューのデザイン タスクを ->** します。 デザイン タスク ウィンドウで、次のようにクリックします。**フォーム テンプレートの発行**オプション。  

12. 発行ウィザード ウィンドウで、次のように選択します。**ネットワークの場所に** をクリック**次**します。  

13. フォーム テンプレートのパスとファイル名 ボックスに、次のように入力します<strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong>と種類**\<MessageType\>** フォーム テンプレートの名前をテキスト ボックスと [] をクリック **[次へ]**。  

14. **[次へ]** をクリックします。  

15. クリックして**パブリッシュと閉じる**します。  

16. Internet Explorer で SharePoint サイトを開いて **http://localhost/sites/bassite/templates**します。  

17. をポイント **\<MessageType\>**、その横にある下矢印をクリックし、順にクリックして、**プロパティの編集**します。  

18. テンプレートで:\< MessageType\>ウィンドウで、[Namespace] ボックスで。  

    - MT の InfoPath フォームを生成している場合に入力します。 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  

    - MX InfoPath フォームを生成している場合に入力します。 <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong>  

       これは、対応するテンプレートを使用してメッセージ インスタンスを特定するに役立ちます。  

19. クリックして**を保存して閉じます**します。
