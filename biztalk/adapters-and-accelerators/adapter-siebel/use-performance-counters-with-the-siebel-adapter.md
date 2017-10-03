---
title: "Siebel アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2540801af6c30632250602b45c21e7b57cd2bc22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a>Siebel アダプターのパフォーマンス カウンターを使用します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムによって作成のパフォーマンス カウンター カテゴリ"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"アダプター パックのインストールと共にします。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB (累積) 時間のパフォーマンス カウンター  
 **BizTalk .NET Adapter for Siebel**カテゴリには 1 つのパフォーマンス カウンター「LOB 時間 (累積)」と呼ばれます。 このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定 Siebel サーバー名については、各操作のパフォーマンス カウンターのインスタンスを作成します。 次のパターンでは、インスタンスが作成されます。  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、エンドポイント id は、接続 URI で指定されている、Siebel サーバーの名前。 操作 id は、によって実行されたアクション、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、ログイン、ログオフ、メタデータ、\<ビジネス コンポーネント名 >.\<操作 >、\<ビジネス サービス名 >.\<ビジネス サービス メソッド > です。 上記の名前付け規則の結果を 127 文字を超える名に次の形式でアクション ID のみが表示されます。  
  
```  
:::<action id>  
```  
  
 場合`:::<action id>`も 127 文字を超える場合、これは 127 文字まで切り捨てられます。  
  
 パフォーマンス カウンターは、アダプターは、Siebel システムへの最初の呼び出し後にのみ初期化されます。 また、 **InstanceLifetime**パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。 
  
> [!NOTE]
>  LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。 設定**EnablePerformanceCounters**にプロパティのバインド**True**パフォーマンス カウンターを有効にします。 パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。 既定では、 **EnablePerformanceCounters**に設定されている**False**です。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**バインディング プロパティの対応するパフォーマンス カウンターの値が変更[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、AppDomain にバインドされ、 **EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。 ただし、ためのバインディング プロパティ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**にどのような値を最後に指定された依存します。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)