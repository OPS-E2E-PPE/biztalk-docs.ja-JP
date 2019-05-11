---
title: SAP アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f83041339275b1b372f57a86754e8df28a24a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372210"
---
# <a name="use-performance-counters-with-the-sap-adapter"></a>SAP アダプターを使用したパフォーマンス カウンターを使用します。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"インストールに沿って、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB の時間 (累積) パフォーマンス カウンター  
 **SAP 向け BizTalk .NET アダプター**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。 このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のパターンでは、パフォーマンス カウンターのインスタンスを作成します。  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 エンドポイントの ID になります。  
  
- (送信) の SAP システムにアダプターからの呼び出し  
  
  -   A、\<アプリケーション サーバーのホスト\>、\<システム番号\>  
  
  -   B、\<メッセージ サーバー ホスト\>、\<R3NAME\>  
  
  -   D、\<変換先\>  
  
- SAP システムからアダプターへの呼び出しの (受信)  
  
  -   I,\<ゲートウェイ ホスト\>、\<ゲートウェイ サーバー\>  
  
  -   ID、\<変換先\>  
  
  操作 ID になります。  
  
- \<RFC 名前\>(の RFC 呼び出しを)  
  
- T、\<RFC 名前\>(の tRFC の呼び出し)  
  
  パフォーマンス カウンターは、アダプターが SAP システムへの最初の呼び出し後にのみ初期化されます。 また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了すると、すぐに存在しなくなることを意味するパフォーマンス カウンターのプロパティが設定されています。
  
> [!NOTE]
>  LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる*EnablePerformanceCounters*します。 パフォーマンス カウンターを有効にするには設定、 *EnablePerformanceCounters*プロパティをバインド**True**します。 パフォーマンス カウンターを無効にするには設定*EnablePerformanceCounters*に**False**します。 既定では、 *EnablePerformanceCounters*に設定されている**False**します。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 *EnablePerformanceCounters*に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、appdomain のバインドと*EnablePerformanceCounters*に設定されているプロパティのバインド**True**で 1 つと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  

[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)