---
title: サービス レベル管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294730"
---
# <a name="service-level-management"></a>サービス レベル管理
AmberPoint SMS サービス レベル マネージャーは、特定のパフォーマンスやエンタープライズ レベルの SOA ベースのシステム内の可用性に関する問題の可視性を提供します。 インストルメント化し、各 Microsoft BizTalk Server 受信場所と送信ポートのメトリックを追跡します。 これは、これらのコンポーネントの継続的なパフォーマンス特性に加え、リアルタイムの正常性と状態表示されます。 図 1 は、受信場所に関連付けられているメトリックの表示を示しています。  
  
 ![AmberPoint 受信場所](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")  
  
 **図 1**  
  
 **受信場所に関連付けられているメトリック**  
  
 AmberPoint の実行時の分析のしきい値を設定し、システムが準拠の警告イベント、コンプライアンス違反イベント、およびコンプライアンスに後続の戻り値を含む、重要なイベントのしきい値を超えたときにアラートを送信できるようにします。 図 2 は、ユーザーがサービス レベル アグリーメントを構成して、このサービス レベル アグリーメントに生成されたアラートの表示の表示を示しています。  
  
 ![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9 AmberPointSLA")  
  
 **図 2**  
  
 **サービス レベル アグリーメントを構成して、通知を表示する画面**  
  
 サービス レベル マネージャー内でパフォーマンスのターゲットを確立することができます。 ソフトウェアでは、これらのターゲットに対するパフォーマンスを測定する、ユーザーのグループからの個々 のメッセージ、特定のユーザーからのメッセージまたはメッセージを追跡します。  
  
 AmberPoint SMS を動的に収集し、図 3 に示すように、メッセージのコンテキストと BizTalk Server を通過するデータを検査するように指示するログ記録のポリシーを構成することもできます。 できますし、使用するこれらのログ「での実行時」のトラブルシューティングのため、技術的な問題、分析するため、およびアーカイブするため業界特有の規制に準拠します。  
  
 ![BizTalk サービスのメッセージ](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")  
  
 **図 3**  
  
 **BizTalk Server サービスのメッセージをログ ファイル**