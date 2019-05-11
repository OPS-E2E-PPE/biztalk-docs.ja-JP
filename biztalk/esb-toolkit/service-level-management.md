---
title: サービス レベルの管理 |Microsoft Docs
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
ms.openlocfilehash: c67b66bf5a353b22193037d7112de8233982834b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394006"
---
# <a name="service-level-management"></a>サービス レベル管理
AmberPoint SMS サービス レベルのマネージャーは、特定のパフォーマンスと SOA ベースのエンタープライズ レベル システム内の可用性の問題を可視化を提供します。 インストルメント化し、各 Microsoft BizTalk Server 受信場所と送信ポートのメトリックを追跡します。 これは、これらのコンポーネントの継続的なパフォーマンス特性に加え、リアルタイムの正常性と状態表示を提供します。 図 1 は、受信場所に関連付けられているメトリックの表示を示します。  
  
 ![AmberPoint 受信場所](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9 AmberPointReceiveLocation")  
  
 **図 1**  
  
 **受信場所に関連付けられているメトリック**  
  
 AmberPoint の実行時の分析のしきい値を設定し、システムが準拠の警告イベント、コンプライアンス違反イベント、およびコンプライアンスに後続の戻り値を含む、重要なイベントのしきい値を超えたときにアラートを送信できるようにします。 図 2 は、ユーザーがサービス レベル アグリーメントを構成して、このサービス レベル アグリーメントに対して生成されたアラートの表示の表示を示しています。  
  
 ![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")  
  
 **図 2**  
  
 **サービス レベル アグリーメントを構成してアラートを表示する画面**  
  
 サービス レベル マネージャー内でパフォーマンスのターゲットを確立することができます。 ソフトウェアでは、これらのターゲットに対するパフォーマンスを測定する、ユーザーのグループから個々 のメッセージ、特定のユーザーからのメッセージまたはメッセージを追跡します。  
  
 AmberPoint SMS を動的に収集し、図 3 に示すように、メッセージのコンテキストと BizTalk Server を通過するデータを検査するように指示するログ記録ポリシーを構成することもできます。 できますし、使用するこれらのログ「にその場で」のトラブルシューティングのため、テクニカル分析の問題、およびアーカイブの業界固有の規制を遵守します。  
  
 ![BizTalk サービスのメッセージ](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9 BizTalkServiceMessages")  
  
 **図 3**  
  
 **BizTalk Server サービスのメッセージをログ ファイル**