---
title: BizTalk ESB Toolkit のサンプル アプリケーション |Microsoft Docs
description: ESB Toolkit のサンプル アプリケーションをインストールして、BizTalk Server で使用する方法のクイック リンクを取得
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: 81f44a6a34493210b44916a8a88cc85ad693480c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975515"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a>BizTalk ESB Toolkit のサンプル アプリケーション
Microsoft BizTalk ESB Toolkit には、いくつかのサンプル アプリケーション インストールして、方法、ESB の機能と、ESB の一部を使用する方法は、パイプライン コンポーネントを実行することができますにはが含まれています。 適応し、独自のアプリケーションのサンプルで使用する手法とコードを変更できます。  
  
## <a name="install-the-sample-applications"></a>サンプル アプリケーションをインストールします。  
  
1. C: ドライブのルートにプロジェクトをという名前のフォルダーを作成し、このフォルダー内で Microsoft.Practices.ESB をという名前のサブフォルダーを作成します。  
  
   > [!NOTE]
   >  現在のリリースで C:\Projects\Microsoft.Practices.ESB フォルダー内に存在するファイルはサポートされているインストールです。 サンプルに付属している BizTalk バインド ファイルは、このパスに依存します。  
  
2. インストールするときに、 [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)ESBSource.zip を指定したインストール場所 (既定では C:\Program files \microsoft BizTalk ESB Toolkit) と呼ばれる .zip ファイルが含まれています。 C:\Projects\Microsoft.Practices.ESB フォルダーに ESBSource.zip ファイルを解凍します。 これは、フォルダーの名前を作成します。**キー**と**ソース**サンプル キーとソース コードとサンプルが含まれています。 ソース フォルダーには、サンプル アプリケーションのソース コードが含まれていて、[キー] フォルダーにサンプル アプリケーションでは、アセンブリの署名に使用される公開キーが含まれています。  
  
3. サンプルを実行する前に、サンプルが正しくインストールするため、C:\Projects\Microsoft.Practices.ESB\ フォルダーに対する読み取り専用属性を削除します。  
  
4. 前に PowerShell スクリプトを使用していない場合は、管理者として PowerShell を開き、次のコマンドを実行する必要があります。  
  
   ```  
   set-executionpolicy unrestricted  
   ```  
  
   > [!NOTE]
   >  PowerShell の詳細については、次を参照してください、 [Windows PowerShell ブログ](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) と[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([ http://go.microsoft.com/fwlink/?LinkId=187594 。](http://go.microsoft.com/fwlink/?LinkId=187594)) msdn です。  
  
5. 管理者としてコマンド プロンプトを開き、WCF スクリプト マップが登録されていることを確認するには、次のコマンドを実行します。  
  
   ```  
   C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
   ```  
  
> [!NOTE]
>  サンプル コードへのアクセスを取得するために、ESBSource.zip ファイルを開く必要があります。  

## <a name="sample-applications"></a>サンプル アプリケーション  
 次のトピックでは、サンプル アプリケーションを記述し、該当する場合は、追加のインストール手順を含めます。  
  
-   [例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [カスタム例外ハンドラーの修復と再送信のサンプルを実行する](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [メッセージ永続化カスタム例外ハンドラーのサンプルを実行する](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [BizTalk エラー メッセージ ルーティング ESB 処理サンプルを実行する](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [スケジュール オンランプ サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [JMS MQRFH2 コンポーネント サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [名前空間コンポーネント サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [変換サービス サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [動的解決サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [BizTalk 操作サンプルのインストールと実行](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [リゾルバー サービス サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [スキャッター/ギャザー サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [メッセージ強化サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [複数の Web サービス サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [デザイナー機能拡張サンプルをインストールし、実行する](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [例外処理サービス サンプルを実行する](../esb-toolkit/running-the-exception-handling-service-sample.md)