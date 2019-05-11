---
title: ホスト インスタンスの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da52cf639cac369198e6fadc9c79dc7e2290a31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305549"
---
# <a name="monitoring-host-instances"></a>ホスト インスタンスの監視
このトピックでは、Microsoft System Center Operations Manager を使用して BizTalk ホスト インスタンスの監視について説明します。  
  
## <a name="using-threshold-rules-to-monitor-health"></a>しきい値規則を使用して、正常性を監視するには  
 BizTalk Server 管理パックには、BizTalk ホストの正常性の包括的なビューを提供するパフォーマンスしきい値ルールが組み込まれています。 しきい値規則の 2 つのさまざまな種類が用意されています。  
  
- 一般的に (たとえば、すべての BizTalk ホストに、すべてのメッセージ ボックス データベースに) 適用される規則です。  
  
- 特定の BizTalk ホストに固有の規則。  
  
  汎用的なルールは、共通のしきい値に基づくすべての BizTalk ホストを監視します。 たとえば、Monitor HostQ サイズ ルールは、共通のしきい値に基づくすべての BizTalk ホストの作業キューを監視します。 3 つの異なるホストがある場合は、そのすべての作業キューが、同じルールで監視し、アラートは、共通のしきい値を越えるホストの作業キューのいずれかが発生しました。  
  
  BizTalk ホストに固有のルールでは、さまざまなホストの別のしきい値を構成できます。 [Biztalkserverapplication] – モニターの HostQ サイズのルールがあるなど、BizTalkServerApplication ホストの作業キューを監視するホスト固有の規則。 この例では、特定のパフォーマンス カウンター インスタンスの特定の Operations Manager プロバイダーを定義し、しきい値規則でそのプロバイダーを使用することができます。 これらの規則は、ホスト固有であるために、新しく作成された各ホストに固有のルールを定義する必要があります。  
  
  BizTalk ホストに固有のルールは、環境内で適用可能なルールを作成するためのテンプレート規則に提供されます。 既定では、すべてのしきい値監視ルールが無効にします。  
  
- 環境内に特定のしきい値の値を汎用的なルールを構成する必要があります。  
  
- テンプレート ルールと適切なしきい値に基づく BizTalk ホストに固有のルールを作成する必要があります。  
  
## <a name="monitoring-biztalk-host-instances"></a>BizTalk ホスト インスタンスの監視  
 特定の BizTalk ホストを対象とするルールは、監視の観点からはより柔軟です。 BizTalk Server 管理パックに用意されている BizTalkServerApplication ホストのすべてのしきい値監視ルールは、テンプレート規則です。 これらの規則を使用するに Operations Manager 管理者コンソールを使用する必要があります。  
  
- 内のテンプレート規則のコピーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルール グループとその名前を変更します。  
  
- BizTalk ホスト固有のパフォーマンス カウンターのインスタンス用の新しい Operations Manager プロバイダーを作成します。  
  
- ルールで使用される Operations Manager のプロバイダーを変更し、新しい 1 つをポイントします。  
  
  たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール BizTalk ホストの ReceiveHost があり、このホストのホスト キューのサイズを監視します。 この場合、BizTalk ホスト キュー サイズのパフォーマンス カウンターの ReceiveHost インスタンスに基づいて Operations Manager プロバイダーを作成する必要があります。 必要があります設定しても、しきい値の値、ルールで適切に環境内の。  
  
  ホスト固有のしきい値監視ルールを使用している場合は、汎用的な監視ルールを無効にする必要があります。 これには、冗長な警告ができないようにします。  
  
## <a name="see-also"></a>参照  
 [System Center Operations Manager 2007 による BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)