---
title: 生成して、SharePoint サイトで MT MX フォームを公開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8bd8248a916d1e98571551a8561119b6377329
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a>生成して、SharePoint サイトで MT/MX フォームの発行
**生成して、SharePoint サイトで MT/MX フォームを公開します。**  
  
1.  フォーム ジェネレーター ユーティリティをダウンロードし、ローカル コンピューターに保存します。  
  
2.  開く、 **FormGenerator.sln**上のダウンロード フォルダーから、ソリューションをコンパイルします。  
  
3.  コマンド プロンプトでコンパイルされた実行可能ファイル (FormGenerator.exe) のフォルダーにアクセスします。 たとえば、デバッグ モードでこのユーティリティを構築した場合は、アクセス、 **.\bin\debug**フォルダーです。  
  
4.  入力 FormGenerator.exe [-b] [-\<いいえ。 テンプレート フォルダーのパスの\>]  
  
     `<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`」を参照してください。 パラメーターを新しく作成したフォルダー名に置き換えます。  
  
5.  上記のコマンドは、MX メッセージの修復に必要なエンベロープ スキーマも生成されます。  
  
6.  出力フォルダーに移動して\<DestinationFolderPath\>です。 \<DestinationFolderPath\>フォームを生成する InfoPath フォーム テンプレートのフォルダーを開きます。 たとえば、MT103 InfoPath フォームを作成する場合は、し、DestinationFolderPath、MT103 フォルダーを開くし、TemplateDS.sln を開きます。  
  
7.  ソリューション エクスプ ローラーでダブルクリックして、 **manifest.xsf**です。 開いたを取得するには、しばらく時間がかかります InfoPath フォームのデザイン ファイルが開きます。  
  
    > [!NOTE]
    >  MX メッセージ manifest.xsf は、2 ~ 5 分に開く取得にかかる場合があります。  
  
8.  Manifest.xsf に移動**ツール]、[フォームのオプション - > セキュリティおよび信頼**メニュー オプション。 チェック、**完全信頼**オプションは、アクセス許可を有効にする必要があります。  
  
9. 選択、**このフォーム テンプレートの署名**チェック ボックスをオンします。 をクリックして**証明書を選択**です。 これには、フォームに署名する証明書を選択します。 **[OK]**をクリックします。  
  
10. 保存**manifest.xsf**です。  
  
11. 移動して**ビューのデザイン タスク]-> [**です。 デザイン タスク] ウィンドウで、をクリックして**フォーム テンプレートの発行**オプション。  
  
12. 発行ウィザード] ウィンドウで次のように選択します。**ネットワークの場所に**] をクリック**次**です。  
  
13. フォーム テンプレートのパスとファイル名] ボックスで、次のように入力します**http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn**および種類** \<MessageType\> 。**フォーム テンプレートの名前をテキスト ボックスとをクリックして**次**です。  
  
14. **[次へ]**をクリックします。  
  
15. をクリックして**発行および閉じる**です。  
  
16. Internet Explorer で、SharePoint サイトを開く**http://localhost/sites/bassite/templates**です。  
  
17. 指す** \<MessageType\>**、横にある下矢印をクリックし、をクリックして、**プロパティの編集**です。  
  
18. テンプレートで:\< MessageType\>ウィンドウで、[Namespace] ボックスで。  
  
    -   MT InfoPath フォームを生成する場合に入力します。 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**  
  
    -   MX InfoPath フォームを生成する場合は、入力: ** http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_ \<MessageName\>**  
  
         これは、対応するテンプレートを使用してメッセージ インスタンスを特定するに役立ちます。  
  
19. をクリックして**を保存して閉じます**です。