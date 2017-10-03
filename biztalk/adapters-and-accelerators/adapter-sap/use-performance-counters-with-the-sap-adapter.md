---
title: "SAP アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5da387377f6201b518d3c5fdf37dabb872bcf600
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-sap-adapter"></a>SAP アダプターのパフォーマンス カウンターを使用します。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するパフォーマンス カウンターを使用することができます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンターのカテゴリを作成します。"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"をインストールするに沿って、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB (累積) 時間のパフォーマンス カウンター  
 **SAP 向け BizTalk .NET Adapter**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。 このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のパターンでは、パフォーマンス カウンターのインスタンスを作成します。  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 エンドポイント ID が考えられます。  
  
-   アダプターから (送信)、SAP システムへの呼び出しの  
  
    -   A、\<アプリケーション サーバーのホスト >、\<システム番号 >  
  
    -   B、\<メッセージ サーバー ホスト >、\<R3NAME >  
  
    -   D、\<先 >  
  
-   SAP システムからアダプターへの呼び出しの (受信)  
  
    -   I,\<ゲートウェイ ホスト >、\<ゲートウェイ サーバー >  
  
    -   ID、\<先 >  
  
 アクション ID が考えられます。  
  
-   \<RFC 名 > の RFC 呼び出し)  
  
-   T、\<RFC 名 > (用 tRFC の呼び出し)  
  
 パフォーマンス カウンターは、アダプターが SAP システムへの最初の呼び出し後にのみ初期化されます。 また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。
  
> [!NOTE]
>  LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている*EnablePerformanceCounters*です。 パフォーマンス カウンターを有効にするには設定、 *EnablePerformanceCounters*にプロパティのバインド**True**です。 パフォーマンス カウンターを無効にする設定*EnablePerformanceCounters*に**False**です。 既定では、 *EnablePerformanceCounters*に設定されている**False**です。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 *EnablePerformanceCounters*に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、AppDomain にバインドされ、 *EnablePerformanceCounters*に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  

[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)