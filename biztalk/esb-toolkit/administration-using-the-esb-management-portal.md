---
title: ESB 管理ポータルを使用して管理 |Microsoft Docs
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
ms.openlocfilehash: 9b0687b57ed18cd657a70ce50f1d1efc284d6392
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379489"
---
# <a name="administration-using-the-esb-management-portal"></a>ESB 管理ポータルを使用した管理
ESB 管理ポータルの一部として含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は、BizTalk ESB Toolkit を拡張するためのメトリックと存在する可能性の使用方法を示すサンプル サイトです。 ポータルでは、独自のカスタマイズされたポータルを作成、開始点を提供します。  
  
 ESB 管理ポータルも非常に有用な対応のツールを使用し、ESB 例外管理システムの効率を最大限に高めることができます。 さらに、ポータル ユーザー インターフェイスを提供 Universal Description, Discovery, and Integration (UDDI) レジストリの基になるサーバーと、監査などの機能をグラフィカルな構成機能の履歴情報の表示を構成します。アラートと通知、およびユーザーができるように ESB アプリケーションで発生している障害を示すアラートを購読します。  
  
 このセクションでは、次を含む、ESB 管理ポータルを使用してを実行できる一般的なタスクについて説明します。  
  
-   [例外とエラー メッセージの使用](../esb-toolkit/working-with-exceptions-and-fault-messages.md)  
  
-   [アラート、通知、サブスクリプションを構成する](../esb-toolkit/configuring-alerts-notifications-and-subscriptions.md)  
  
-   [監査と履歴を表示し、管理する](../esb-toolkit/viewing-and-managing-auditing-and-history.md)  
  
-   [グラフとレポートを利用してエラー傾向を分析する](../esb-toolkit/analyzing-fault-trends-using-charts-and-reports.md)  
  
-   [UDDI 登録を表示し、発行する](../esb-toolkit/viewing-and-publishing-uddi-registrations.md)  
  
> [!NOTE]
>  ESB 管理ポータルの個々 の機能の詳細については、次を参照してください。 [ESB 管理ポータル機能リファレンス](../esb-toolkit/esb-management-portal-feature-reference.md)します。  
  
## <a name="esb-portal-technologies"></a>ESB ポータル テクノロジ  
 ESB 管理ポータルでは、次のテクノロジを利用します。  
  
- [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] 
  
- ASP.NET
  
- [Enterprise Library](http://go.microsoft.com/fwlink/?LinkId=188292) ([http://go.microsoft.com/fwlink/?LinkId=188292](http://go.microsoft.com/fwlink/?LinkId=188292))。 ESB 管理ポータルでは、次のエンタープライズ ライブラリ アセンブリを使用します。  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Caching**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Common**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Data**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ExceptionHandling.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Logging**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.ObjectBuilder2**  
  
  -   **Microsoft.Practices.EnterpriseLibrary.Validation**  
  
  -   Microsoft.Practices.Unity  
  
- [Microsoft Chart Controls](http://go.microsoft.com/fwlink/?LinkId=188293) (http://go.microsoft.com/fwlink/?LinkId=188293) for Microsoft .NET Framework 4  
  
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理システムの障害の追跡のみにメトリックの追跡を拡張します。