---
title: "ホスト グループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host groups, privileges
- Windows groups, host groups
- host groups, Windows groups
- host groups, about host groups
- host groups
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e3798e42442e1a6533e4f286d194c8e2474be6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="host-groups"></a>ホスト グループ
ホスト グループは、インプロセスの BizTalk ホスト (BizTalk Server のホスト プロセス) に対するアクセスに使用するアカウントの Windows グループ (既定で BizTalk アプリケーション ユーザー グループという名前) です。 使用している環境のインプロセス ホストごとに 1 つのホスト グループを使用することをお勧めします。  
  
 ホストは 1 つの Windows グループとのみ関連付けることができます (と呼ばれる、*ホスト グループ*)。 ホスト グループには、すべての関連する BizTalk Server データベースの SQL Server ログインと権限が必要です。 ホストをホスト グループに関連付けると、ホストにホスト グループの権限が付与されます。  
  
 構成ウィザードでホストを作成し、ホストに対してローカル Windows グループを指定すると、構成ウィザードは、自動的に 2 つの Windows グループを作成します。 これらのグループの既定の名前は、BizTalk アプリケーション ユーザー グループと BizTalk 分離ホスト ユーザー グループです。  
  
 ホスト グループに関連付けられているホストのホスト インスタンスを作成すると、ホスト インスタンスは、ホスト グループのデータベース権限を継承します。  
  
 ホスト グループは、ホストの WMI (Windows Management Instrumentation) オブジェクトのプロパティです。 ホストにホスト インスタンスがない場合は、ホストが属する Windows グループを変更できます。  
  
 ホストを作成する際、ホストが属するホスト グループを指定します。 BizTalk WMI プロバイダーは、ホスト グループが持つ権限 (たとえば、SQL Server ログインとデータベース ユーザー アクセスを含むランタイム機能に必要な BizTalk Server 権限) をホストに付与します。 BizTalk Server WMI プロバイダーがホスト グループの権限をホスト インスタンスに付与するため、ホスト インスタンスを作成する際には、正しいサービス アカウント (ホスト) を指定する必要があります。  
  
> [!NOTE]
>  ローカルのホスト グループを作成する場合、ローカル Windows グループを作成し、グループのメンバーとしてドメイン ユーザーを割り当てることができます。 ホストに対してローカル Windows グループを指定すると、ドメイン ユーザーおよびローカル ユーザーのどちらであるかに関係なく、ホスト インスタンスのログオン ユーザーとして Windows グループのメンバーを使用できます。  
  
 ホスト グループには、次の権限が必要です。  
  
-   ホスト グループは、次のデータベースの BTS_HOST_USERS SQL Server ロールのメンバーである必要がある。  
  
    -   BizTalk 管理 ([!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] では構成データベースと呼ばれる)  
  
    -   メッセージ ボックス  
  
    -   ルール エンジン  
  
    -   Tracking  
  
    -   BAM プライマリ インポート  
  
-   Bts _ のメンバーである必要があります、\<インプロセス ホスト名\>メッセージ ボックス データベースの SQL Server ロールを (_u)  
  
-   BAM プライマリ インポート データベースの BAM_EVENT_WRITER SQL Server ロールのメンバーである必要がある。  
  
> [!NOTE]
>  追跡ホストとしてホストを指定すると、BizTalk Server 管理コンソールは、追跡データベースの SQL Server ロールから BizTalk ホスト グループを自動的に削除します。 BizTalk ホスト グループは、BizTalk 管理データベースとメッセージ ボックス データベースの SQL Server ロールから手動で削除する必要があります。 追跡ホストとしてホストを指定する方法については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [エンティティ](../core/entities.md)