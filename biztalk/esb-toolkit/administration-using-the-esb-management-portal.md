---
title: ESB の管理ポータルを使用して管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 478d1dcc-e9b2-443b-be98-5b7545322401
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351d06df4d6384607564778c4b86d8c509379488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290274"
---
# <a name="administration-using-the-esb-management-portal"></a>ESB の管理ポータルを使用して管理
一部として含まれる、ESB 管理ポータル、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、BizTalk ESB Toolkit を拡張するためのメトリックと存在する可能性の使用方法を示すサンプル サイトです。 ポータルでは、カスタマイズした独自のポータルをビルドすることができます開始ポイントを提供します。  
  
 ESB 管理ポータルが使用して、ESB 例外管理システムの効率を最大化するのに役立つ高対応していて、役立つツールもできます。 さらに、ポータル ユーザー インターフェイスを提供 Universal Description, Discovery, and Integration (UDDI) レジストリの基になるサーバーおよび監査などの機能のグラフィカルな構成機能の履歴情報の表示を構成します。アラートと通知、およびユーザーを許可する ESB アプリケーションで発生するエラーを示すアラートにサブスクライブします。  
  
 このセクションでは、次を含む、ESB 管理ポータルを使用してを実行できる一般的なタスクについて説明します。  
  
-   [例外とエラー メッセージを使用します。](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [アラート、通知、およびサブスクリプションを構成します。](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [表示と管理の監査および履歴](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [グラフとレポートを使用してフォールト傾向の分析](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [表示して、UDDI の登録を公開](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  ESB の管理ポータルの個々 の機能の詳細については、次を参照してください。 [ESB 管理ポータル機能リファレンス](../esb-toolkit/esb-management-portal-feature-reference.md)です。  
  
## <a name="esb-portal-technologies"></a>ESB ポータル テクノロジ  
 ESB の管理ポータルでは、次のテクノロジを活用します。  
  
-   [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
-   ASP.NET
  
-   [エンタープライズ ライブラリ](http://go.microsoft.com/fwlink/?LinkId=188292)([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。 ESB の管理ポータルでは、次のエンタープライズ ライブラリ アセンブリを使用します。  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
    -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
    -   Microsoft.Practices.Unity  
  
-   [Microsoft Chart コントロール](http://go.microsoft.com/fwlink/?LinkId=188293)(http://go.microsoft.com/fwlink/?LinkId=188293) の Microsoft .NET Framework 4  
  
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理システムの障害の追跡にのみメトリックの追跡を拡張します。