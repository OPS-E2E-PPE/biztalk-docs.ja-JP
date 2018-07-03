---
title: .NET CLR 設定を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe3d54aa508d45211277377c2f2d8880c37044d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015155"
---
# <a name="how-to-modify-net-clr-settings"></a>.NET CLR の設定を変更する方法
BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を更新するには、BizTalk 設定ダッシュボードを使用して、CLR (共通ランタイム言語) Hosting の値を変更できます。 このトピックでは、これらの設定を変更する手順を説明します。  

## <a name="prerequisites"></a>前提条件  
 ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a>ホスト インスタンスの .NET CLR 設定を変更するには  

1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  

2. **BizTalk 設定ダッシュ ボード**] ダイアログ ボックスの [、**ホスト インスタンス**タブをクリックし、 **.NET CLR**タブ。  

3. 以下を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**変更を適用し、設定ダッシュ ボードを終了します。  


   |     プロパティ      |                                                                                目的                                                                                | 境界値 | 既定値 | アップグレード ロジック |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | **ホスト インスタンス** | ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューター上のホストで実行中のインスタンスを選択します。 |        -        |       -       |       -       |

    **スレッドの設定**  

   |プロパティ|目的|境界値|既定値|アップグレード ロジック|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |**最大値。ワーカー スレッド**|.NET CLR ワーカー スレッドの最大数を指定します。|[最小ワーカー スレッド数、500]|25|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
   |**最小ワーカー スレッド数**|.NET CLR ワーカー スレッドの最小数を指定します。|[0, 500]|5|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
   |**最大値。IO スレッドの数**|IO スレッドの最大数を指定します。|[最小 IO スレッド数、1000]|250|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  
   |**最小値。IO スレッドの数**|IO スレッドの最小数を指定します。|[0, 1000]|25|ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。|  

    .NET CLR 設定は、コア CPU ごとに適用されます。  

   > [!NOTE]
   >  既定の設定を復元するには、次のようにクリックします。**既定値に戻す**します。  

   > [!NOTE]
   >  **ワーカー スレッド**キューに置かれた作業項目の処理に使用し、 **I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理するために、I/O 完了ポートに関連付けられています。  

   > [!NOTE]
   >  BizTalk は、hkey_local_machine \system\currentcontrolset\services\btssvc$ 内の値を前のバージョンからアップグレードした場合は*hostname*\CLR Hosting レジストリ キーを設定ダッシュ ボードに設定されます。  

## <a name="see-also"></a>参照  
 [ホスト インスタンスの設定を変更する方法](../core/how-to-modify-host-instance-settings.md)