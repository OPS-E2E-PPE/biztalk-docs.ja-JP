---
title: SQL Server とアダプター クライアント上の MSDTC の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f609b3d54c9b2db6ad576eab75bb82872075f5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013827"
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a>SQL Server とアダプターのクライアントで MSDTC を構成します。
SQL Server を使用して、操作を実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。 クライアント プログラムは、1 つ以上のトランザクション リソースを同じトランザクションの一部としては場合、トランザクションは MSDTC トランザクションに昇格を取得します。 MSDTC トランザクションのスコープ内での操作を実行するアダプターを有効にするのには、実行しているコンピューターで両方の MSDTC を構成する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server。 また、Windows ファイアウォールの例外の一覧に、MSDTC を追加する必要があります。 このセクションでは、アダプターのクライアントと SQL Server を実行するコンピューターでこれらのタスクを実行する方法について説明します。  
  
> [!NOTE]
>  使用して SQL サーバーの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]常に 2 つのリソースが含まれます: SQL Server と SQL Server 上に存在する BizTalk メッセージ ボックスに接続するアダプター。 そのため、すべての操作は実行を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC トランザクションのスコープ内で実行されます。 使用するため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC を常に有効にする必要があります。  
> 
> [!NOTE]
>  操作は、アダプター クライアントは、データを書き込めません Select 操作など、SQL Server データベースのトランザクション内で操作を実行するは、追加のオーバーヘッドをしない可能性があります。 このような場合は、構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を設定して、トランザクションのコンテキストなしの操作を実行する、 **UseAmbientTransaction**プロパティをバインド**false**します。 バインディング プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 このような場合にも MSDTC を構成する必要はありません。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
  
1. 開いている**コンポーネント サービス**します。  

   または、**サーバー マネージャー**、**ツール**、し、**コンポーネント サービス**。  
  
2. 展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**、選び**プロパティ**します。  
  
3. **[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。 

   - **ネットワーク DTC アクセス**
   - **リモート クライアントを許可します。** 
   - **受信を許可する** 
   - **送信を許可する** 
   - **必要ない Authetnication**
  
4. **[OK]** を選択して変更を保存します。  
  
5. MSDTC サービスを再起動するメッセージが表示されたら、選択**はい**します。 MSDTC サービスが再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>MSDTC を Windows ファイアウォールの例外リストに追加します。  

> [!TIP] 
>  Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既に許可場合があります。 そうである場合は、受信の規則として表示されます。 表示されない場合は、このセクションを使用して、MSDTC を許可します。 

1.  開いている**Windows ファイアウォール**を選択し、**詳細設定**左側にします。  

    または、**サーバー マネージャー**、**ツール**、し、**セキュリティが強化された Windows ファイアウォール**。  
  
2.  右クリックして**受信の規則**、選択および**新しいルール**します。  
  
3.  ウィザード。 

    1. 選択**プログラム**を選択し、**次**します。 
    2. 設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**します。  
    3. **接続を許可する**、選び**次**します。
    4. 選択**ドメイン**を選択し、**次**します。
    5. などの任意の名前を入力します`MSDTC for Oracle EBS`、選び**完了**します。
  
5.  ウィザードを完了し、Windows ファイアウォールを閉じます。 
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)