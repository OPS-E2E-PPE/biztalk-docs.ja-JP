---
title: "新しいホストを作成 |Microsoft ドキュメント"
descriptions: Use BizTalk Administration to create a new host in BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 811e6e57-5c37-471a-aff4-5b2b68c367b1
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700f0bb43a4f31b76819e7aca6fe5895cc2b6ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-new-host"></a>新しいホストを作成します。
BizTalk ホストとは、アダプター ハンドラー、受信場所 (パイプラインを含む)、オーケストレーションなどのアイテムの論理的なコンテナーです。 セキュリティ対策のため、およびホストの管理を容易にするために、メッセージの処理、受信、および送信用の各ホストを分離し、信頼済みのアイテムとそうでないアイテムのホストを使い分けることをお勧めします。 BizTalk サーバーごとにインストールできるホストのインスタンスは 1 つだけです。 ホストの詳細については、次を参照してください。[ホスト](../core/hosts.md)です。  
  
 Windows Management Instrumentation (WMI) を使用して、新しいホストを作成する方法については、次を参照してください。 **MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="prerequisites"></a>前提条件  
 ホストの作成、ホスト プロパティの変更、およびホストの削除には、次のユーザー権利が必要です。  
  
-   BizTalk Server 管理者グループのメンバーである必要があります。  
  
-   SQL Server には次の権利が必要です。  
  
    -   SQL Server の管理者または BizTalk 追跡 (BizTalk DTADb) データベース、メッセージ ボックス (BizTalkMsgBoxDb) データベース、および BAM プライマリ インポート (BAMPrimaryImport) の db_owner または db_securityadmin SQL Server データベース ロールのメンバーのいずれかにする必要があります。データベースです。  
  
    -   メッセージ ボックス データベースが存在するすべてのコンピューターの sysadmin SQL Server ロールのメンバーであるか、すべてのメッセージ ボックス データベースの db_owner または db_ddladmin SQL Server ロールのメンバーである必要があります。  
  
## <a name="steps"></a>手順
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、クリックして**ホスト**です。  
  
3.  詳細ウィンドウで右クリック**ホスト**、 をクリックして**新規**、クリックして**ホスト**です。  
  
4.  **ホストのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|ホストの名前を表示します。 ホストには作成時に名前を付けます。 ホスト名の長さは 80 文字以下にしてください。|  
    |**型**|ホストの種類を表示します。 インプロセス ホストでは、オーケストレーションと、特定の送信ハンドラーや受信ハンドラーをホストできます。 分離ホストは、BizTalk Server 外部のプロセス境界であり、特定の送信ハンドラーと受信ハンドラーで必要です。 インプロセス ホストにオーケストレーションを参加させることができます。インプロセス ホストでは、送信ハンドラーまたは受信ハンドラーをホストできます。|  
  
     **および**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホストの追跡を許可します。**|ホストで、状態監視データおよびビジネス データを処理する場合は、このチェック ボックスをオンにします。 このチェック ボックスをオンにすると、現在のホストには、メッセージ ボックス データベースの追跡テーブルおよび BizTalk 追跡データベースに対する読み取りと書き込みの特権が与えられます。 これに伴い、このホスト内で実行されるオブジェクトにも、これらのデータベースに対する読み取りと書き込みのアクセス許可が与えられます。 このチェック ボックスをオフにすると、ホストには、メッセージ ボックス データベース内の追跡テーブルへの書き込みアクセスだけが許可され、BizTalk 追跡データベースへのアクセスは許可されません。|  
    |**信頼されている認証**|BizTalk Server でこのホストを信頼する場合は、このチェック ボックスをオンにします。|  
    |**32 ビットのみ**|このチェック ボックスをオンにすると、ホスト インスタンス プロセスが、32 ビット サーバーおよび 64 ビット サーバーの両方で 32 ビットとして作成されます。 このチェック ボックスをオフにすると、ホスト インスタンス プロセスは、32 ビット サーバー上では 32 ビットとして、64 ビット サーバー上では 64 ビットとして作成されます。|  
    |**やすいように、既定のホスト グループ内**|このホストを既定のホストにする場合は、このチェック ボックスをオンにします。 作成されたポートおよびオーケストレーションでは、明示的に別のホストを選択しない限り、オーケストレーションのホストとして既定のホストが自動的に使用されます。 このチェック ボックスがオンの状態で使用不可になっている場合、ホストは既定のホストです。|  
    |**Windows グループ**|ホストのローカル グループまたはドメイン グループを入力します。 この Windows グループのメンバーには、このホストのインスタンスの実行権限が与えられます。|  
  
5.  **証明書** タブで、次の操作をクリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**共通名**|表示されている解読証明書の説明を表示します。|  
    |**拇印**|このホストからの受信メッセージを解読するために使用する秘密キー証明書の拇印を表示します。 証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。|  
    |**証明書を削除します。**|表示されている解読証明書をホストから削除する場合にクリックします。|  
    |**参照**|クリックすると表示、 **Windows セキュリティ**ダイアログ ボックスで、現在のユーザーまたはホストで使用する個人用ストアから解読証明書を選択します。|  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト プロパティを変更します。](../core/how-to-modify-host-properties.md)   
 [ホストを削除します。](../core/how-to-delete-a-host.md)