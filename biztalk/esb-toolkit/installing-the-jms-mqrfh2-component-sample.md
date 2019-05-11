---
title: JMS MQRFH2 コンポーネント サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d1ddc49c882ecff05083e9a0a38357733f7f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249765"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>JMS MQRFH2 コンポーネント サンプルをインストールします。
このサンプルで使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次をインストールすることも必要があります。  
  
- IBM WebSphere MQ 5.3 (で CSD12)、WebSphere MQ 6.x または WebSphere MQ 7.0  
  
- IBM"RfhUtil"JMS テスト キューとメッセージを取得するためのユーティリティ  
  
  JMS MQRFH2 コンポーネント サンプルでは、JMS MQRFH2 コンポーネント、Microsoft BizTalk Server のインストール フォルダーとアセンブリをグローバル アセンブリ キャッシュ内に存在する対応するスキーマの PipelineComponents フォルダー内に存在する必要があります。 インストール、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core は自動的にコピーして、適切な場所にアセンブリをインストールします。 ただし、必要な場合、これらのタスクを手動で実行することができます。  
  
  **JMS MQRFH2 コンポーネントとスキーマを手動でインストールするには**  
  
1. Microsoft.Practices.ESB.JMS.PipelineComponents.dll アセンブリを BizTalk Server のインストール フォルダーの PipelineComponents フォルダーにコピーします。  
  
2. Microsoft.Practices.ESB.JMS.Schemas.Property.dll、.NET Framework 構成ツールを使用してグローバル アセンブリ キャッシュには、管理ツール セクションにあるスキーマ アセンブリを追加、**開始**メニュー。  
  
   このセクションでは、GlobalBank.JMS BizTalk アプリケーションに JMS MQRFH2 サンプルをインストールするプロセスについて説明します。 このサンプルをインストールする前に」の説明に従って、ESB Toolkit のコアをインストールする必要があります[BizTalk ESB Toolkit のコアをインストールする](http://go.microsoft.com/fwlink/?LinkId=187612)([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。  
  
   ソリューションのプロジェクトから JMS MQRFH2 コンポーネント サンプルをインストールまたはに付属する Windows インストーラー ファイルを使用することができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 このセクションでは、次のトピックについて説明します。  
  
-   [インストール スクリプトを利用し、JMS MQRFH2 サンプルをインストールする](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [JMS MQRFH2 コンポーネント サンプルによりインストールされるアセンブリとアイテム](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [JMS MQRFH2 サンプル インストールをテストする](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)