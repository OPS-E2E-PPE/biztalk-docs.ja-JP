---
title: BizTalk で、Oracle E-business Suite のアプリケーションの開発 |Microsoft Docs
description: WCF を使用して Oracle EBS アプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7b1ebff-b3f8-4e07-a089-d1d5bfb78d56
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc00f1b22777829b314ccd1171cbc7fb6b4e5ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972819"
---
# <a name="develop-your-oracle-e-business-suite-applications"></a>Oracle E-business Suite アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の成果物の操作を呼び出します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消費されることができます。  
  
- 物理ポートのバインドを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- クライアント プロキシのインスタンスでメソッドの呼び出し。  
  
- によって、WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk と WCF サービスと WCF チャネル 
  
 次の表では:  
  
- Oracle E-business Suite で実行できるさまざまな操作の一覧を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
- 選択した方法を使用して、タスクの実行に関する情報を格納しているトピックへのリンクを提供します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデルまたは WCF チャネル モデル)。  
  
|演算|BizTalk Server|WCF サービス モデル|WCF チャネル モデル|  
|---|---|---|---|  
|インターフェイス テーブルとビューに対する操作の実行 | [挿入、更新、削除、またはインターフェイス テーブルと Oracle E-business suite のインターフェイス ビューに対する select](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-or-select-on-interface-tables-and-views-with-oracle-ebs.md) |[挿入、更新、削除、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューで操作を選択します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[WCF チャネル モデルを使用して Oracle E-business Suite でのインターフェイス テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)|  
|大規模なデータ型を持つテーブルとビューの操作を実行します。 | [WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md) |[WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-table-operations-with-large-data-types-in-oracle-ebs-using-a-wcf-service.md)||  
|Oracle データベースでの複合操作を実行します。 | [Oracle E-business Suite での複合操作を完了します。](../../adapters-and-accelerators/adapter-oracle-ebs/complete-composite-operations-on-oracle-e-business-suite.md)|||  
|Oracle E-business Suite での同時実行プログラムを呼び出す | [Oracle E-business Suite での同時実行プログラムを起動します。](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-concurrent-programs-in-oracle-e-business-suite.md) | [WCF サービス モデルを使用して Oracle E-business Suite での同時実行プログラムを起動します。](../../adapters-and-accelerators/adapter-oracle-ebs/run-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Oracle E-business Suite の起動要求を設定します。 | [Oracle E-business Suite での要求のセットを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite.md) | [WCF サービス モデルを使用して Oracle E-business Suite での要求のセットを呼び出す](../../adapters-and-accelerators/adapter-oracle-ebs/invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作を実行します。| [Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-or-executenonquery-in-oracle-e-business-suite.md) |[WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-oracle-ebs/executereader-executescalar-executenonquery-in-oracle-ebs-with-a-wcf-service.md)||  
|ポーリングの Oracle データベースを使用して BizTalk Server|[BizTalk Server を使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)|[WCF サービス モデルを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)||  
|Oracle E-business Suite から受信側のデータベース変更通知|[BizTalk Server を使用して Oracle データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[WCF サービス モデルを使用して Oracle E-business Suite データベース変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-the-wcf-service-model.md)|[SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)|  

## <a name="next-steps"></a>次のステップ  
 このセクションのトピックでは提供情報、手順、および例を使用するアプリケーションの開発に役立つ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].NET ソリューションのプログラミングとします。 
  
-   [Oracle EBS への接続を作成する](create-a-connection-to-oracle-e-business-suite.md)
-   [Visual Studio で Oracle EBS 操作用のメタデータを取得する](get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)
-   [バインド プロパティの操作](read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)
-   [ポーリングに基づいたデータ変更メッセージを受信する](receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)
-   [MSDTC を使用してトランザクションを有効にする](enable-ms-dtc-to-allow-transactions-for-oracle-e-business-suite-adapter.md)
-   [Oracle EBS アダプターを使用して BizTalk アプリケーションを開発する](develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)
-   [WCF サービス モデルを使用してアプリケーションを開発する](develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)
-   [WCF チャネル モデルを使用してアプリケーションを開発する](develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)
-   [SharePoint で Oracle EBS アダプターを使用する](use-the-oracle-e-business-suite-adapter-with-sharepoint.md)
-   [サンプル](samples-for-the-oracle-ebs-adapter.md)
-   [トランザクションのプロパティとアプリケーションのコンテキストを構成する](configure-transaction-properties-and-application-context-in-oracle-ebs-adapter.md)
  
