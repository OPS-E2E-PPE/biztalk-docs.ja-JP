---
title: "ホスト インスタンスの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41dd0e01aa1e28862a3e99cfc767b3dd6ddec3c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-host-instances"></a>ホスト インスタンスの監視
このトピックでは、Microsoft System Center Operations Manager を使用して BizTalk ホスト インスタンスの監視について説明します。  
  
## <a name="using-threshold-rules-to-monitor-health"></a>しきい値規則を使用して正常性を監視するには  
 BizTalk Server 管理パックには、BizTalk ホストのヘルスの包括的なビューを提供するパフォーマンスのしきい値規則が組み込まれています。 次の 2 種類のしきい値ルールがあります。  
  
-   一般的に (と例については、すべての BizTalk ホストにすべてのメッセージ ボックス データベースに) 適用される規則です。  
  
-   特定の BizTalk ホストに固有の規則。  
  
 汎用的なルールは、共通のしきい値に基づくすべての BizTalk ホストを監視します。 たとえば、ルール Monitor HostQ Size は、共通のしきい値に基づくすべての BizTalk ホストの作業キューを監視します。 3 つの異なるホストがある場合は、そのすべての作業キューが、同じルールによって監視され、共通のしきい値を越える任意のホストの作業キューに警告が発生しました。  
  
 BizTalk ホストに固有の規則を使用すると、別のホストの別のしきい値を構成できます。 たとえば、Monitor HostQ Size – BizTalkServerApplication ルールは、BizTalkServerApplication ホストの作業キューを監視するホスト固有の規則です。 この例では、特定のパフォーマンス カウンターのインスタンスの特定の Operations Manager プロバイダーを定義し、しきい値規則でそのプロバイダーを使用できます。 これらの規則は、ホストに固有であるために、新しく作成された各ホストに固有の規則を定義する必要があります。  
  
 BizTalk ホストに固有のルールは、ルールを作成するためのテンプレート規則は、環境に適用できるように提供されます。 既定では、すべてのしきい値監視ルールが無効に設定されています。  
  
-   環境には、特定のしきい値の値を汎用的なルールを構成してください。  
  
-   テンプレート規則と適切なしきい値に基づいて BizTalk ホストに固有のルールを作成する必要があります。  
  
## <a name="monitoring-biztalk-host-instances"></a>BizTalk ホスト インスタンスの監視  
 特定の BizTalk ホストを対象とするルールは、監視の観点からより柔軟です。 BizTalk Server 管理パックで提供される、BizTalkServerApplication ホストのすべてのしきい値監視ルールでは、テンプレート ルールです。 これらの規則を使用するのには、Operations Manager 管理者コンソールを使用してください。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ルール グループのテンプレート ルールのコピーを作成して、その名前を変更します。  
  
-   BizTalk ホスト固有のパフォーマンス カウンター インスタンスの新しい Operations Manager プロバイダーを作成します。  
  
-   ルールで使用される Operations Manager プロバイダーを変更し、新しいものをポイントします。  
  
 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールは、BizTalk ホストの ReceiveHost があり、このホストのホスト キューのサイズを監視します。 この場合、BizTalk ホストのキューのサイズのパフォーマンス カウンターの ReceiveHost インスタンスに基づいて Operations Manager プロバイダーを作成する必要があります。 また、ルールのしきい値を、使用する環境に応じて設定する必要があります。  
  
 ホスト固有のしきい値監視ルールを使用している場合は、汎用的な監視ルールを無効にする必要があります。 これにより、冗長な警告が防止されます。  
  
## <a name="see-also"></a>参照  
 [System Center Operations Manager 2007 による BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)