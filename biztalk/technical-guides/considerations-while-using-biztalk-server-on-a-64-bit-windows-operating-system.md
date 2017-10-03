---
title: "64 ビット Windows オペレーティング システムで BizTalk Server を使用するときの考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac630f55-7ebe-4b93-bf98-70b00788520f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71287d29d13406d3f1159054e988ef0e2b98a648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system"></a>64 ビット Windows オペレーティング システムで BizTalk Server を使用するときの考慮事項
使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット Windows オペレーティング システムでは、このトピックで説明されている問題を考慮することを確認します。 よくある質問 Microsoft の 64 ビット サポートに関連する[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を参照してください[BizTalk Server の 64年ビット サポート](http://go.microsoft.com/fwlink/?LinkID=155306)(http://go.microsoft.com/fwlink/?LinkID=155306)。  
  
## <a name="modify-the-process-memory-usage-throttling-threshold"></a>プロセスのメモリ使用量が制限のしきい値を変更します。  
 既定では、**プロセス メモリの使用状況**ホスト制限のしきい値は 25 に設定します。 この値を超えた場合、BizTalk プロセスのメモリ使用量は 300 MB よりも制限の条件が発生します。 64 ビット サーバー上には、100 にこの値を大きくことができます。 これにより、多くのメモリ消費量、BizTalk プロセスで調整が行われる前にします。 プロセス メモリ使用量ホスト制限のしきい値を変更する方法の手順については、次を参照してください。[ホストの制限の既定の設定を変更する方法](http://go.microsoft.com/fwlink/?LinkId=157210)(http://go.microsoft.com/fwlink/?LinkId=157210)。  
  
> [!NOTE]  
>  システムに 2 GB 以上の物理メモリが存在している場合でも、使用できる最大のプロセス メモリは、この計算のために 2 GB のアドレス空間サイズに制限されます。 プロセス メモリの 2 GB までの制限は、32 ビット システムと 64 ビット システムの両方でこの計算のために使用されます。 メモリ不足エラーを回避するのにはお勧めはできるようにするホスト インスタンスのメモリを 32 ビットまたは 64 ビットのオペレーティング sy BizTalk Server がインストールされている場合に関係なく、BizTalk Server の 32 ビット版を実行するときに、1.54 GB を超える値が指定されていないこと発生することができます。 たとえば、この設定に 1 ～ 100 の値を指定して使用されるプロセス メモリの割合に基づく調整を開始する場合、75 (.75 * 2 GB = 1.54 GB) より大きい値を入力しないでください。 1536.If より大きい値を入力しないを mb 単位で指定した数に基づく調整を開始するには、この設定を 100 より大きい値を指定する場合は、64 ビット バージョンの BizTalk Server を実行している、指定値または 100 (100%) または 2048 (2 GB) を開始するには 2 GB の利用可能な最大のプロセス メモリの使用を調整します。  
  
## <a name="adapters-that-do-not-support-64-bit-hosts"></a>64 ビットのホストをサポートしないアダプター  
 次のアダプターは、64 ビット ホスト インスタンスで実行するはサポートされません。  
  
-   FTP アダプター  
  
-   POP3 アダプター  
  
 32 ビット ホスト インスタンスでこれらのアダプターを実行することを確認してください。  
  
## <a name="configure-the-mimesmime-encoder-to-run-in-32-bit-mode"></a>32 ビット モードで実行する、MIME/SMIME エンコーダーを構成します。  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、MIME/SMIME エンコーダー パイプライン コンポーネントがなくなるがいないネイティブの 64 ビット サポートをしています。 つまり、このコンポーネントは、32 ビットのエミュレーション モード プロセス (WOW64) で実行する必要があります。 このため、このエンコーダー コンポーネント (または、元の送信パイプライン) を実行するホスト インスタンスは、32 ビットのエミュレーション モードで実行する必要があります。 このホスト インスタンスで BizTalk の他の要素を実行する場合、64 ビット サポートがないという制約がパフォーマンスなどに影響を与えることに注意してください。