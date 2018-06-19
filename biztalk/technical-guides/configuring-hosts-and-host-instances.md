---
title: ホストとホスト インスタンスの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 55dda06d447d9e27c7c8b491986b499003c0bb73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300114"
---
# <a name="configuring-hosts-and-host-instances"></a>ホストとホスト インスタンスを構成します。
BizTalk ホストを展開することができますを 0 個以上の実行時プロセスの論理セットを表します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services との成果物 (アダプター ハンドラー、受信場所、オーケストレーション)。 ホスト インスタンスを実行しているコンピューター上のホストの物理インスタンス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 BizTalk ホストとホスト インスタンスの詳細については、次を参照してください。[ホスト](http://go.microsoft.com/fwlink/?LinkId=154189)(http://go.microsoft.com/fwlink/?LinkId=154189) および[ホスト インスタンス](http://go.microsoft.com/fwlink/?LinkId=154190)(http://go.microsoft.com/fwlink/?LinkId=154190)。  
  
 BizTalk ホストとホスト インスタンスの管理に関する詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](http://go.microsoft.com/fwlink/?LinkId=154191)(http://go.microsoft.com/fwlink/?LinkId=154191)。  
  
 専用の追跡ホストを構成する方法については、次を参照してください。[専用追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)です。  
  
## <a name="separating-host-instances-by-functionality"></a>機能別のホスト インスタンスを分離します。  
 に加えて、高可用性には、ホスト インスタンスの構成の点が、送信、受信、処理、および複数のホストに追跡機能を分離する必要があります。 これは、BizTalk グループで、ワークロードを構成する際の柔軟性を BizTalk グループ全体で処理を分散する主な手段です。 その他のホストに影響を与えずに 1 つのホストを停止するこれもできます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースで発生するメッセージの受信の受信状態のままする可能性があります。  
  
 機能別のホスト インスタンスを分離すると、次の利点も提供されます。  
  
-   各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、およびスレッドなどのリソースの独自セットがあります。  
  
-   複数の BizTalk ホストでは、各ホストには、メッセージ ボックス データベースに独自の作業キュー テーブルが割り当てられているために、メッセージ ボックス データベースのホスト キュー テーブルでの競合も減少します。  
  
-   実装されて調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト レベルです。 これにより、ホストごとに異なる調整特性を設定することができます。  
  
-   ホスト レベルのセキュリティが実装されます。各ホストは、個別の Windows id で実行されます。 これは、ようにすると、たとえば、与える**Host_A**へのアクセスを**FileShare_B**、中に、いずれかのファイル共有にアクセスするその他のホストを許可していません。  
  
    > [!NOTE]  
    >  追加のホスト インスタンスを作成する利点があるときに欠点がありますも潜在的な多数のホスト インスタンスが作成される場合。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成し、コンピューターのリソース (CPU、メモリ、スレッド) などを使用する Windows サービス (BTSNTSvc.exe または BTSNTSvc64.exe) です。  
  
 変更の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストのプロパティを参照してください[ホストのプロパティを変更する方法](http://go.microsoft.com/fwlink/?LinkId=154192)(http://go.microsoft.com/fwlink/?LinkId=154192)。  
  
##  <a name="BKMK_MemLimit"></a>32 ビットの BizTalk ホスト インスタンスのメモリ使用量の最大の実用的な制限  
 3 GB のセットを 32 ビット Windows オペレーティング システムで 32 ビット プロセスには 3 ギガバイト (GB) のアドレス指定可能なメモリがあるプロセスが「大きいアドレスに注意してください」である場合 (実行可能ファイルは、イメージのヘッダーに設定 IMAGE_FILE_LARGE_ADDRESS_AWARE フラグ)。  「大規模なアドレスに注意してください」で、BizTalk ホスト プロセスは、3 GB のセットでの Windows オペレーティング システム上のメモリのうち 3 GB に対処できます。  同様に、64 ビット Windows オペレーティング システム (AMD64) 上の 32 ビット プロセスでは、プロセスが「大きいアドレスに注意してください」である場合、4 GB のアドレス指定可能なメモリがあります。  もう一度、BizTalk ホスト プロセス「大規模なアドレスに注意してください」、解決できる 4 GB のメモリ 64 ビット Windows オペレーティング システムで 32 ビット プロセスとして実行します。 64 ビット Windows オペレーティング システム (AMD64) 上の 64 ビット プロセスでは、アドレス指定可能なメモリの 8 テラバイトがあります。  
  
 場合でも、(3 GB スイッチなし) には、32 ビット Windows オペレーティング システム上のプロセスによってアドレス指定可能な最大メモリが 2 GB の場合は、「仮想バイト」が 2 GB になる前にメモリ不足エラー (BizTalk ホスト インスタンスの場合) などの .NET アプリケーションが表示されます。 次の表は、これをまとめたものし、仮想バイトとプライベート バイトの実質的な制限値が含まれています。  
  
|[処理]|Windows OS|(大きいアドレス対応プロセス) を使用してアドレス指定可能なメモリ|Virtual Bytes の実際の制限|PrivateBytes の実際の制限|  
|-------------|----------------|---------------------------------------------------------------|---------------------------------------|--------------------------------------|  
|32 ビット|32 ビット|2 GB|1400 MB|800 MB|  
|32 ビット|3 gb スイッチの 32 ビット|3 GB|2400 MB|1800 MB|  
|32 ビット|64 ビット|4 GB|3400 MB|2,800 MB|  
|64 ビット|64 ビット|8 テラバイト|-|-|  
  
 詳細については、以下をご覧ください。  
  
-   [ASP.NET のパフォーマンスの監視、および管理者に警告する](http://go.microsoft.com/fwlink/?LinkId=151856)(http://go.microsoft.com/fwlink/?LinkId=151856)  
  
-   [Windows のリリースでのメモリ制限](http://go.microsoft.com/fwlink/?LinkId=151857)(http://go.microsoft.com/fwlink/?LinkId=151857)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server を構成します。](../technical-guides/checklist-configuring-biztalk-server.md)   
 [専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)