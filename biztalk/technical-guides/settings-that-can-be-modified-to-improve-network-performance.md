---
title: "ネットワーク パフォーマンスを向上させる変更可能な設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c4b32a5a5f588e76d155c2f8d052398f1a247
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a>ネットワーク パフォーマンスを向上するように変更する設定
このトピックでは、ネットワーク パフォーマンスに影響する推奨値の説明を提供します。  
  
> [!IMPORTANT]  
>  このガイドを完了したパフォーマンスのテスト中に Windows Server 2008 が既定ではチューニングするが表示されることが確認されました。 レジストリ設定の変更は、システムへの影響を慎重に分析した後にのみ実行する必要があります。  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a>MaxUserPort と TcpTimedWaitDelay 設定を調整します。  
 **MaxUserPort**値アプリケーションは、システムから利用可能なユーザーの任意のポートを要求するときに使用される最大ポート数を制御します。 通常、短時間のポートは、1025 65535 までからの範囲で割り当てられます。 ポートの範囲は、実際に開始点とは、エンドポイントとの範囲ではようになりました。 新しい既定の開始ポートは 49152、および既定の終了ポートは 65535 です。 この範囲は、アプリケーションとサービスによって使用される既知のポートだけでなく、します。 各サーバーでは、サーバーで使用するポートの範囲を変更できます。 この範囲を調整するには、netsh コマンドを使用して次のようにします。  
  
 **netsh int \<ipv4 (& a) #124; ipv6 > 動的設定\<tcp (& a) #124; udp > 開始番号 num = 範囲を =**  
  
 このコマンドは、tcp 動的ポートの範囲を設定します。 開始ポート アドレスが**数**、ポートの総数と**範囲**です。 サンプル コマンドは、次のとおり: 次の netsh コマンドを使用して動的ポートの範囲を表示することができます。  
  
-   netsh int ipv4 では、動的 tcp を表示します。 Tcp v4 の最大許容値の範囲を向上させるのには、次のコマンドを使用します。  
  
     **netsh int ipv4 設定動的 tcp 開始 1025 num = 64511 を =**  
  
-   netsh int ipv4 動的 udp を表示します。  
  
-   netsh int ipv6 動的 tcp を表示します。  
  
-   netsh int ipv6 動的 udp を表示します。  
  
 **TcpTimedWaitDelay**値が閉じられるときに、接続が TIME_WAIT 状態で保持される時間の長さを指定します。 接続が TIME_WAIT 状態のときに、ソケット ペアを再利用できません。 これは、値が 2 回セグメントの最大有効期間中、ネットワーク上にする必要があります 2 msl 状態とも呼ばれます。 詳細については、次を参照してください。[インターネット RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (ハイパーリンク"http://go.microsoft.com/fwlink/?LinkId=113719"http://go.microsoft.com/fwlink/?LinkId=113719)。 TcpTimedWaitDelay 設定を調整するには、次に示すようにレジストリ設定を変更する必要があります。  
  
###  
  
|||  
|-|-|  
|キー:|HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters|  
|[値]: |TcpTimedWaitDelay|  
|データ型:|REG_DWORD|  
|範囲:|30 ~ 300 (10 進数)|  
|既定値:|0x78 (120 10 進数)|  
|推奨値:|30|  
|既定値が存在するか。|**いいえ**、追加する必要があります。|  
  
## <a name="see-also"></a>参照  
 [ネットワークのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-network-performance.md)