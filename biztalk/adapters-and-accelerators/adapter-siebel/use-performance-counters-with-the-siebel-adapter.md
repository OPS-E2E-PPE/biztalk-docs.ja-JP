---
title: Siebel アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79bb582ca3f79dc20f537551d9aeb98db5cd6cc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370349"
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a>Siebel アダプターを使用したパフォーマンス カウンターを使用します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"アダプター パックのインストールと共にします。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB の時間 (累積) パフォーマンス カウンター  
 **BizTalk .NET Adapter for Siebel**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。 このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定 Siebel サーバー名の各操作のパフォーマンス カウンターのインスタンスを作成します。 次のパターンでは、インスタンスが作成されます。  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エンドポイントの id は、接続 URI で指定されている、Siebel サーバーの名前。 アクション id の操作によって実行される可能性があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、ログイン、ログオフ、メタデータ、\<ビジネス コンポーネント名\>.\<操作\>、\<ビジネス サービス名\>.\<ビジネス サービス メソッド\>します。 前の名前付け規則の結果を 127 文字を超える名前の場合は、次の形式でアクション ID のみが表示されます。  
  
```  
:::<action id>  
```  
  
 場合`:::<action id>`もが 127 文字を超える、127 文字までには切り捨てられます。  
  
 パフォーマンス カウンターは、アダプターは、Siebel システムへの最初の呼び出しを後でのみ初期化されます。 また、 **InstanceLifetime** 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了すると、すぐに存在しなくなることを意味するパフォーマンス カウンターのプロパティが設定されています。 
  
> [!NOTE]
>  LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。 設定**EnablePerformanceCounters**プロパティをバインド**True**パフォーマンス カウンターを有効にします。 パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。 既定では、 **EnablePerformanceCounters**に設定されている**False**します。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**バインディング プロパティの対応するパフォーマンス カウンターの値を変更する[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、appdomain のバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**で 1 つと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。 ただし、ためのバインディング プロパティ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**にどのような値を最後に指定された依存します。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)