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
ms.openlocfilehash: 512907afe143b92af3eafea2156efd42d97f4f75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384602"
---
# <a name="how-to-modify-net-clr-settings"></a>.NET CLR 設定を変更する方法
BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を更新するには、BizTalk 設定ダッシュ ボードを使用して、適切な共通ランタイム (CLR 言語) Hosting 値を変更できます。 このトピックでは、これらの設定を変更するための手順を提供します。  

## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a>ホスト インスタンスの .NET CLR 設定を変更するには  

1. **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。  

2. **BizTalk 設定ダッシュ ボード**] ダイアログ ボックスの [、**ホスト インスタンス**タブをクリックし、 **.NET CLR**タブ。  

3. 以下を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**変更を適用し、設定ダッシュ ボードを終了します。  


   |     プロパティ      |                                                                                目的                                                                                | 境界値 | 既定値 | アップグレード ロジック |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | **ホスト インスタンス** | ホストの実行中のインスタンスを選択、ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。 |        -        |       -       |       -       |

    **スレッドの設定**  

   |プロパティ|目的|境界値|既定値|アップグレード ロジック|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |**最大値。ワーカー スレッド**|.NET CLR ワーカー スレッドの最大数を指定します。|[最小ワーカー スレッド、500]|25|ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。|  
   |**最小ワーカー スレッド数**|.NET CLR ワーカー スレッドの最小数を指定します。|[0, 500]|5|ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。|  
   |**最大値。IO スレッドの数**|IO スレッドの最大数を指定します。|[最小 IO スレッド数、1000]|250|ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。|  
   |**最小値。IO スレッドの数**|IO スレッドの最小数を指定します。|[0, 1000]|25|ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。|  

    .NET CLR 設定は、コア CPU ごとに適用されます。  

   > [!NOTE]
   >  既定の設定を復元するには、次のようにクリックします。**既定値に戻す**します。  

   > [!NOTE]
   >  **ワーカー スレッド**キューに置かれた作業項目の処理に使用し、 **I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理するために、I/O 完了ポートに関連付けられています。  

   > [!NOTE]
   >  BizTalk は、hkey_local_machine \system\currentcontrolset\services\btssvc$ 内の値を前のバージョンからアップグレードした場合は*hostname*\CLR Hosting レジストリ キーを設定ダッシュ ボードに設定されます。  

## <a name="see-also"></a>参照  
 [ホスト インスタンスの設定を変更する方法](../core/how-to-modify-host-instance-settings.md)