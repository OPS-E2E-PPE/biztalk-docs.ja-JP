---
title: セキュリティで保護されたアーキテクチャの設計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cacd6bf8414ac91e2fb6d7846fd3b650c90b6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351682"
---
# <a name="designing-a-secure-architecture"></a>セキュリティで保護されたアーキテクチャの設計
BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 トピックに示されているアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱性のある潜在的なセキュリティ脅威の多くを解決します。 ただし、ビジネス資産、ビジネス、および資産を保護するための最適なアーキテクチャを特定する、潜在的な脅威を軽減するために使用可能なリソースである問題のある脅威を評価する必要があります。 このセクションでは、設計するときに検討する追加のセキュリティ オプション、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。  
  
## <a name="firewalls"></a>ファイアウォール  
 物理的な (ハードウェア) ファイアウォールまたはソフトウェア ファイアウォールを使用すると、環境内のリソースへのアクセスを制限します。 トピックの中に[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)Forefront Threat Management Gateway (TMG) 2010 を使用してサーバーを作成同様のアーキテクチャ ハードウェアまたはサード パーティのソフトウェアのファイアウォールを使用する開くと、さまざまな BizTalk Server コンポーネント間の通信に必要なポートを構成します。 BizTalk Server で使用するポートの詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。  
  
## <a name="active-directory"></a>Active Directory  
 サンプルの配置、Active Directory® ディレクトリ サービスは、各サーバー グループの周囲のハード セキュリティ境界の作成に使用されます。 一方向の信頼では、BizTalk Server がアプリケーションのデータ ドメインで作成されたアカウントで実行すると、処理サーバーで実行されている他の BizTalk Server 以外のアプリケーションでの欠陥が原因の攻撃から BizTalk Server 環境をさらに保護できます。 データ ドメインが、他のドメインのアカウントを信頼していないため、別のドメイン内のアカウントのセキュリティ侵害は侵害状態から BizTalk Server 環境を保持します。  
  
## <a name="ipsec-and-ssl"></a>IPSec および SSL  
 環境内には重要なは、ファイアウォールのセキュリティのレベルを必要とする脅威を提供するが、処理、データを接続するネットワーク セグメントを引き起こすことはありませんし、サービスのドメインがさまざまなネットワーク攻撃 (パケットから物理的にセキュリティで保護された場合スニッフィングまたは改ざん) 別に 1 つのサーバーから移動すると、データを保護する必要があります。 この場合、1 つのサーバーからのトラフィックの暗号化には、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用できます。  
  
## <a name="see-also"></a>参照  
 [分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md)   
 [セキュリティの計画](../core/planning-for-security.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)