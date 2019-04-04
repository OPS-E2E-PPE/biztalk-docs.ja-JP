---
title: BizTalk Server を使用して、64 ビット Windows オペレーティング システム上の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac630f55-7ebe-4b93-bf98-70b00788520f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486df5450c01b51426383e7ab7a3d100013c23dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990579"
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a>BizTalk Server を使用して、64 ビット Windows オペレーティング システム上の考慮事項
使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット Windows オペレーティング システムでは、このトピックで説明されている問題を考慮することを確認します。 よく寄せられる質問については、Microsoft BizTalk Server の 64 ビットのサポートに関連した、次を参照してください。 [BizTalk Server の 64 ビット サポート](http://go.microsoft.com/fwlink/?LinkID=155306)(<http://go.microsoft.com/fwlink/?LinkID=155306>)。  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a>プロセスのメモリ使用量が制限のしきい値を変更します。  
 既定で、**プロセスのメモリ使用率**ホスト制限のしきい値は 25 に設定します。 この値を超えた場合、BizTalk プロセスのメモリ使用量は 300 MB よりも、制限の条件が発生します。 64 ビット サーバーでこの値を 100 に増やすことできます。 これにより、メモリ消費量の詳細、BizTalk プロセスによって調整が発生する前に。 プロセス メモリ使用量ホスト制限のしきい値を変更する方法の手順については、[ホスト制限の既定の設定を変更する方法](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)を参照してください。  
  
> [!NOTE]  
>  システムに 2 GB 以上の物理メモリが存在している場合でも、使用できる最大のプロセス メモリは、この計算のために 2 GB のアドレス空間サイズに制限されます。 プロセス メモリの 2 GB までの制限は、32 ビット システムと 64 ビット システムの両方でこの計算のために使用されます。 メモリ不足エラーを回避するにはお勧めできるようにするホスト インスタンスのメモリを 32 ビットまたは 64 ビットのオペレーティング sy に BizTalk Server がインストールされている場合に関係なく、BizTalk Server の 32 ビット バージョンを実行するときに、1.54 GB を超える値が指定されていないこと理工系します。 たとえば、この設定に 1 ～ 100 の値を指定して使用されるプロセス メモリの割合に基づく調整を開始する場合、75 (.75 * 2 GB = 1.54 GB) より大きい値を入力しないでください。 1536.If より大きい値を入力しないでください (mb)、指定した数に基づく調整を開始するには、この設定を 100 より大きい値を指定する場合は、64 ビット バージョンの BizTalk Server を実行している、指定の値または 100 (100%) または 2048 (2 GB) を開始するには 2 GB の最大利用可能なプロセスのメモリを使用する場合を調整します。  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a>64 ビットのホストをサポートしないアダプター  
 64 ビット ホスト インスタンスで実行するは、次のアダプターはサポートされていません。  
  
- FTP アダプター  
  
- POP3 アダプター  
  
  32 ビット ホスト インスタンスでこれらのアダプターを実行することを確認します。  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a>32 ビット モードで実行する MIME/SMIME エンコーダーを構成します。  
 BizTalk Server で、MIME/SMIME エンコーダー パイプライン コンポーネントが停止しないネイティブの 64 ビット サポートがあります。 つまり、このコンポーネントは、32 ビットのエミュレーション モード プロセス (WOW64) で実行する必要があります。 このため、このエンコーダー コンポーネント (または、元の送信パイプライン) を実行するホスト インスタンスは、32 ビットのエミュレーション モードで実行する必要があります。 このホスト インスタンスで BizTalk の他の要素を実行する場合、64 ビット サポートがないという制約がパフォーマンスなどに影響を与えることに注意してください。