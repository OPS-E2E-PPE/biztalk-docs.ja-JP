---
title: ".NET CLR 設定を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d134faf06aebbb24cafd716722d63172a5ceb68b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-net-clr-settings"></a>.NET CLR の設定を変更する方法
BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を更新するには、BizTalk 設定ダッシュボードを使用して、CLR (共通ランタイム言語) Hosting の値を変更できます。 このトピックでは、これらの設定を変更する手順を説明します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a>ホスト インスタンスの .NET CLR 設定を変更するには  
  
1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード**ダイアログ ボックスの**ホスト インスタンス**タブをクリックし、 **.NET CLR**タブです。  
  
3.  次の操作を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**を変更を適用し、設定ダッシュ ボードを終了します。  
  
    |プロパティ|目的|境界値|既定値|アップグレード ロジック|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**ホスト インスタンス**|ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューター上のホストで実行中のインスタンスを選択します。|-|-|-|  
  
     **スレッドの設定**  
  
    |プロパティ|目的|境界値|既定値|アップグレード ロジック|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**最大値。ワーカー スレッド**|.NET CLR ワーカー スレッドの最大数を指定します。|[最小ワーカー スレッド数、500]|25|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
    |**最小ワーカー スレッド数**|.NET CLR ワーカー スレッドの最小数を指定します。|[0, 500]|5|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
    |**最大値。IO スレッド数**|IO スレッドの最大数を指定します。|[最小 IO スレッド数、1000]|250|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
    |**最小値。IO スレッド数**|IO スレッドの最小数を指定します。|[0, 1000]|25|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
  
     .NET CLR 設定は、コア CPU ごとに適用されます。  
  
    > [!NOTE]
    >  既定の設定を復元する をクリックして**既定値に戻す**です。  
  
    > [!NOTE]
    >  **ワーカー スレッド**キューに置かれた作業項目の処理に使用して**I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理する I/O 完了ポートに関連付けられています。  
  
    > [!NOTE]
    >  BizTalk が、hkey_local_machine \system\currentcontrolset\services\btssvc$ 内の値、以前のバージョンからアップグレードした場合*hostname*\CLR Hosting レジストリ キーを設定ダッシュ ボードに設定されます。  
  
## <a name="see-also"></a>参照  
 [ホスト インスタンスの設定を変更する方法](../core/how-to-modify-host-instance-settings.md)