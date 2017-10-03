---
title: "JMS MQRFH2 コンポーネント サンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b522d986524c77a53cf5a847f749a9ce41e2c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>JMS MQRFH2 コンポーネント サンプルをインストールします。
このサンプルを使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次をインストールすることも必要があります。  
  
-   IBM WebSphere MQ 5.3 (CSD12) の WebSphere MQ 6.x または WebSphere MQ 7.0  
  
-   IBM"RfhUtil"JMS テスト キューとメッセージを取得するためのユーティリティ  
  
 JMS MQRFH2 コンポーネント サンプルには、Microsoft BizTalk Server のインストール フォルダーとグローバル アセンブリ キャッシュに存在する対応するスキーマの PipelineComponents フォルダー内に存在する JMS MQRFH2 コンポーネントが必要です。 インストール、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コアは自動的にコピーして、適切な場所にアセンブリをインストールします。 ただし、必要な場合、これらのタスクを手動で実行することができます。  
  
 **JMS MQRFH2 コンポーネントとスキーマを手動でインストールするには**  
  
1.  Microsoft.Practices.ESB.JMS.PipelineComponents.dll アセンブリを BizTalk Server のインストール フォルダーの PipelineComponents フォルダーにコピーします。  
  
2.  .NET Framework 構成ツールを使用して、グローバル アセンブリ キャッシュに Microsoft.Practices.ESB.JMS.Schemas.Property.dll セクションにある、管理ツールのスキーマ アセンブリを追加、**開始**メニュー。  
  
 このセクションでは、GlobalBank.JMS BizTalk アプリケーションに JMS MQRFH2 サンプルをインストールするプロセスについて説明します。 このサンプルをインストールする前に」の説明に従って、ESB Toolkit のコアをインストールする必要があります[BizTalk ESB Toolkit のコアをインストールする](http://go.microsoft.com/fwlink/?LinkId=187612)([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。  
  
 ソリューションのプロジェクトから、JMS MQRFH2 コンポーネント サンプルをインストールまたはに付属する Windows インストーラー ファイルを使用することができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 このセクションのトピックは次のとおりです。  
  
-   [インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [アセンブリおよび JMS MQRFH2 コンポーネント サンプルがインストールされているアイテム](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [JMS MQRFH2 サンプルのインストールをテストします。](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)