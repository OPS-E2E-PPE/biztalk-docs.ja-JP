---
title: "BizTalk ESB Toolkit のサンプル アプリケーション |Microsoft ドキュメント"
description: "ESB Toolkit のサンプル アプリケーションをインストールし、BizTalk Server で使用する方法についてクイック リンク"
caps.latest.revision: "5"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-sample-applications"></a>BizTalk ESB Toolkit のサンプル アプリケーション
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 動作、およびその用途、ESB のパイプライン コンポーネントを表示する、いくつかのサンプル アプリケーションをインストールして実行が含まれています。 調整して、独自のアプリケーションのサンプルで使用される手法とコードを変更することができます。  
  
## <a name="install-the-sample-applications"></a>サンプル アプリケーションをインストールします。  
  
1.  C: ドライブのルートでプロジェクトをという名前のフォルダーを作成し、このフォルダー内で Microsoft.Practices.ESB をという名前のサブフォルダーを作成します。  
  
    > [!NOTE]
    >  現在のリリースでサポートされているインストールは C:\Projects\Microsoft.Practices.ESB フォルダー内に存在するファイルです。 サンプルに付属している BizTalk バインド ファイルは、このパスによって異なります。  
  
2.  インストールするときに、 [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)、という名前の指定したインストール場所に ESBSource.zip の .zip ファイルが含まれています (既定では、C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)])。 C:\Projects\Microsoft.Practices.ESB フォルダーに ESBSource.zip ファイルを解凍します。 フォルダーの名前を作成これ**キー**と**ソース**サンプル キーとコードとソース コード サンプルが含まれています。 ソース フォルダーには、サンプル アプリケーションのソース コードとキー フォルダーには、サンプル アプリケーションでアセンブリの署名に使用される公開キーが含まれています。  
  
3.  サンプルを実行する前に、サンプルが正常にインストールできるように、C:\Projects\Microsoft.Practices.ESB\ フォルダーの読み取り専用の属性を削除します。  
  
4.  前に PowerShell スクリプトを使用していない場合は、管理者として PowerShell を開き、次のコマンドを実行する必要があります。  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  PowerShell の詳細については、次を参照してください、 [Windows PowerShell のブログ](http://go.microsoft.com/fwlink/?LinkId=187593)([http://go.microsoft.com/fwlink/?。LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) および[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) MSDN のです。  
  
5.  管理者としてコマンド プロンプトを開き、WCF スクリプト マップが登録されていることを確認するには、次のコマンドを実行します。  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  サンプル コードへのアクセスを取得するために、ESBSource.zip ファイルを開く必要があります。  

## <a name="sample-applications"></a>サンプル アプリケーション  
 次のトピックでは、サンプル アプリケーションについて説明し、該当する場合は、追加のインストール手順を含めます。  
  
-   [例外の管理のサンプルをインストールします。](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [修復と再送信のカスタム例外ハンドラーのサンプルを実行しています。](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [カスタム例外ハンドラーのサンプルを保持するメッセージを実行しています。](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [メッセージのルーティング ESB 処理サンプル BizTalk を実行できませんでした。](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [インストールして、Itinerary ランプでサンプルを実行します。](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [インストールして、JMS MQRFH2 コンポーネント サンプルを実行します。](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [インストールして、Namespace コンポーネント サンプルを実行します。](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [インストールして、変換サービス サンプルを実行します。](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [インストールして、動的な解決サンプルを実行します。](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [インストールして、BizTalk Operations サンプルを実行します。](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [インストールして、リゾルバー サービスのサンプルを実行しています。](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [インストールして、スキャッター/ギャザー サンプルを実行します。](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [インストールして、メッセージ強化サンプルを実行します。](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [インストールして、複数の Web サービス サンプルを実行します。](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [インストールして、デザイナーの機能拡張のサンプルを実行します。](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [例外処理サービスのサンプルを実行しています。](../esb-toolkit/running-the-exception-handling-service-sample.md)