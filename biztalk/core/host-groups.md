---
title: ホスト グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e56411a55fefd4c54c1a0583b619e68b868e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344273"
---
# <a name="host-groups"></a>ホスト グループ

## <a name="overview"></a>概要
ホスト グループ (既定では、BizTalk Application Users グループをという名前)、Windows グループでは、インプロセス BizTalk ホスト (BizTalk Server ホスト プロセス) へのアクセス権を持つアカウントを使用します。 環境内で、インプロセス ホストごとに 1 つのホスト グループを使用することをお勧めします。  
  
 1 つの Windows グループにのみ、ホストを関連付けることができます (と呼ばれる、*ホスト グループ*)。 ホスト グループは、関連するすべての BizTalk Server データベースで SQL Server ログインと特権が必要です。 ホストをホスト グループに関連付けると、ホストにホスト グループの権限を付与します。  
  
 ホストを作成、構成ウィザードを使用するホストに使用するローカル Windows グループを指定する場合は、構成ウィザードは自動的に 2 つの Windows グループを作成します。 これらのグループの既定の名前は、BizTalk Application Users グループと BizTalk 分離ホスト ユーザー グループです。  
  
 ホスト グループに関連付けられているホストのホスト インスタンスを作成するときに、ホスト インスタンスは、ホスト グループのデータベースの権限を継承します。  
  
 ホスト グループは、ホストの Windows Management Instrumentation (WMI) オブジェクトのプロパティです。 ホストのホスト インスタンスがない場合に、ホストが属する Windows グループを変更することができます。  
  
 ホストが属するホストを作成するときに、ホスト グループを指定するとします。 BizTalk WMI プロバイダーは、ホスト グループをホストに (たとえば、SQL Server ログインとデータベース ユーザーへのアクセスなど、ランタイム機能に必要な BizTalk Server の特権など) には、特権を付与します。 指定してください、正しいサービス アカウント (ホスト)、ホスト インスタンスを作成するときに、BizTalk Server WMI プロバイダーがホスト グループの権限を付与するため、ホスト インスタンスに。  
  
> [!NOTE]
>  ローカルのホスト グループを作成する場合は、ローカル Windows グループを作成し、グループのメンバーとしてドメイン ユーザーを割り当てます。 ホストのローカル Windows グループを指定する場合、Windows グループのメンバーでドメインまたはローカルのユーザーがいるかどうか使用できますホスト インスタンスのログオン ユーザーとして。  

## <a name="required-permissions"></a>必要な権限  
 ホスト グループには、次の特権が必要です。  
  
-   次のデータベースの BTS_HOST_USERS SQL Server ロールのメンバーの可能性があります。  
  
    -   BizTalk 管理 
  
    -   メッセージ ボックス  
  
    -   ルール エンジン  
  
    -   Tracking  
  
    -   BAM プライマリ インポート  
  
-   Bts _ のメンバーである必要があります、\<インプロセス ホスト名\>メッセージ ボックス データベースの SQL Server ロールを (_u)  
  
-   BAM プライマリ インポート データベースの BAM_EVENT_WRITER SQL Server ロールのメンバーであるする必要があります。  
  
> [!NOTE]
>  追跡ホストとしてホストを指定すると、追跡データベースの SQL Server ロールから BizTalk ホスト グループは、BizTalk Server 管理コンソールによって自動的に削除されます。 BizTalk 管理データベースとメッセージ ボックス データベースの SQL Server ロールから BizTalk ホスト グループを手動で削除する必要があります。 追跡ホストとしてホストを指定する方法の詳細については、次を参照してください。[ホスト プロパティの変更](../core/how-to-modify-host-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [エンティティ](../core/entities.md)