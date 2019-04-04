---
title: ホストとホスト インスタンスの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a36a73a4-cc5f-47d6-b56f-7871684c4489
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 286bdaaff66cf0b85caa3bb169bb506501ff386f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969003"
---
# <a name="configuring-hosts-and-host-instances"></a>ホストとホスト インスタンスを構成します。
BizTalk ホストは、展開することができますを 0 個以上の実行時プロセスの論理セットを表します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスおよび成果物 (アダプター ハンドラー、受信場所、およびオーケストレーション)。 ホスト インスタンスが実行しているコンピューター上のホストの物理インスタンス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 BizTalk ホストとホスト インスタンスの詳細については、次を参照してください。[ホスト](http://go.microsoft.com/fwlink/?LinkId=154189)(<http://go.microsoft.com/fwlink/?LinkId=154189>) と[ホスト インスタンス](http://go.microsoft.com/fwlink/?LinkId=154190)(<http://go.microsoft.com/fwlink/?LinkId=154190>)。  
  
 BizTalk ホストとホスト インスタンスの管理に関する詳細については、[BizTalk ホストの管理およびホスト インスタンス](http://go.microsoft.com/fwlink/?LinkId=154191)(http://go.microsoft.com/fwlink/?LinkId=154191)を参照してください。  
  
 専用の追跡ホストを構成する方法については、[専用の追跡ホストを構成する](../technical-guides/configuring-a-dedicated-tracking-host.md)を参照してください。  
  
## <a name="separating-host-instances-by-functionality"></a>機能別のホスト インスタンスを分離します。  
 ホスト インスタンスの構成の高可用性の側面だけでなく送信、受信、処理、および複数のホストに追跡機能を分離する必要があります。 これは柔軟に、BizTalk グループで、ワークロードを構成するときに、BizTalk グループ間での処理の分散の主要な手段です。 これにより他のホストに影響を与えずに 1 つのホストを停止することもできます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースで発生するメッセージの受信の受信を許可する一方する可能性があります。  
  
 機能別のホスト インスタンスを分離することでは、次の利点も用意されています。  
  
- 各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、スレッドなどのリソースの独自セットがあります。  
  
- 複数の BizTalk ホストは、各ホストには、独自の作業キュー テーブル、メッセージ ボックス データベースが割り当てられているために、メッセージ ボックス データベースのホスト キュー テーブルでの競合も軽減されます。  
  
- 調整の実装は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト レベル。 これにより、各ホストの制限は異なる特性を設定することができます。  
  
- ホスト レベルのセキュリティが実装されます。各ホストは、個別の Windows id の下で実行されます。 これは、ようにすると、たとえば、提供する**Host_A**へのアクセスを**FileShare_B**、いずれかのファイル共有にアクセスするその他のホストを許可していないときにします。  
  
  > [!NOTE]  
  >  追加のホスト インスタンスを作成する利点はありますも潜在的な欠点が多すぎるのホスト インスタンスが作成された場合です。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成およびコンピューターのリソース (CPU、メモリ、スレッド) などを利用する Windows サービス (BTSNTSvc.exe または BTSNTSvc64.exe) です。  
  
  変更の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストのプロパティを参照してください[ホスト プロパティを変更する方法](http://go.microsoft.com/fwlink/?LinkId=154192)(<http://go.microsoft.com/fwlink/?LinkId=154192>)。  
  
##  <a name="BKMK_MemLimit"></a> 32 ビットの BizTalk ホスト インスタンスのメモリ使用量の最大の実質的な制限  
 プロセスが「大きいアドレスに注意してください」の場合、3 GB のセットを 32 ビット Windows オペレーティング システム上の 32 ビット プロセスは 3 ギガバイト (GB) のアドレス指定可能なメモリをある (つまり IMAGE_FILE_LARGE_ADDRESS_AWARE フラグがイメージ ヘッダーの設定には、実行可能ファイル)。  BizTalk ホスト プロセスは、「大きなアドレスに注意してください」、3 GB の 3 GB のセットでの Windows オペレーティング システム上のメモリ アドレス指定できます。  同様に、64 ビット Windows オペレーティング システム (AMD64) 上の 32 ビット プロセスでは、プロセスが「大規模なアドレスに注意してください」の場合、4 GB のアドレス指定可能なメモリがあります。  ここでも、BizTalk ホスト プロセスでは、「大きなアドレスに注意してください」、アドレス指定できます 4 GB のメモリ 64 ビット Windows オペレーティング システムで 32 ビット プロセスとして実行されている場合。 64 ビット Windows オペレーティング システム (AMD64) 上の 64 ビット プロセスでは、8 テラバイトのアドレス指定可能なメモリがあります。  
  
 場合でも、(3 GB スイッチ) なしの 32 ビット Windows オペレーティング システム上のプロセスによってアドレス指定可能な最大メモリが 2 GB は、「仮想バイト」が 2 GB になる前にメモリ不足エラー (BizTalk ホスト インスタンスの場合) などの .NET アプリケーションが表示されます。 次の表では、これをまとめていて、仮想バイトとプライベート バイトの実質的な制限が含まれています。  
  
|Process|Windows OS|(大きいアドレスの認識プロセス) を使用してアドレス指定可能なメモリ|仮想バイトの実際の制限|PrivateBytes の実際の制限|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 ビット|32 ビット|2 GB|1400 MB|800 MB|  
|32 ビット|32 ビット 3 GB|3 GB|2400 MB|1800 MB|  
|32 ビット|64 ビット|4 GB|3400 MB|2800 MB|  
|64 ビット|64 ビット|8 テラバイト|-|-|  
  
 詳細については、以下をご覧ください。  
  
-   [ASP.NET パフォーマンスの監視、および管理者に警告する](http://go.microsoft.com/fwlink/?LinkId=151856)(http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Windows のリリースのメモリ制限](http://go.microsoft.com/fwlink/?LinkId=151857)(http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)   
 [専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)