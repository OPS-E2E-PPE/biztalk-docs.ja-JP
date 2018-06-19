---
title: SQL Server とアダプターのクライアント上の MSDTC を構成する |Microsoft ドキュメント
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
ms.openlocfilehash: cf519044dc28d417d85682189dd4a52585310ac0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222922"
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a>SQL Server とアダプターのクライアント上の MSDTC を構成します。
SQL Server を使用して、操作を実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (を通じて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデルで、または WCF チャネル モデル)、トランザクション スコープ内で実行することができます。 場合は、クライアント プログラムは、同じトランザクションの一部として 1 つ以上のトランザクション リソースを持つ、トランザクションが MSDTC トランザクションに昇格を取得します。 MSDTC トランザクションのスコープ内で操作を実行するアダプターを有効にするを実行しているコンピューターで MSDTC を両方を構成する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server。 また、Windows ファイアウォールの例外の一覧に、MSDTC を追加する必要があります。 このセクションでは、アダプターのクライアントと SQL Server を実行するコンピューターでこれらのタスクを実行する方法に関する情報を提供します。  
  
> [!NOTE]
>  SQL Server を使用して操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]常に 2 つのリソースが含まれます: SQL Server と SQL Server 上に存在する BizTalk メッセージ ボックスに接続するアダプター。 そのため、すべての操作は実行を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC トランザクションのスコープ内で実行されます。 使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC を常に有効にする必要があります。  
  
> [!NOTE]
>  場所アダプター クライアントは、データに書き込みません、Select 操作などの SQL Server データベースの操作のトランザクション内の操作を実行するは、追加のオーバーヘッドをしない可能性があります。 構成することができます、このような場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を設定してトランザクション コンテキストを使用せずに操作を実行する、 **UseAmbientTransaction**にプロパティのバインド**false**です。 バインディング プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 このような場合にも MSDTC を構成する必要はありません。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
  
1.  開いている**コンポーネント サービス**です。  

    または、**サーバー マネージャー****ツール**、し、**コンポーネント サービス**です。  
  
2.  展開**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**、展開**分散トランザクション コーディネーター**、右クリック**ローカル DTC**を選択して**プロパティ**です。  
  
3.  **[セキュリティ]** タブをクリックします。このタブでは、次のすべてを選択します。 

  - **ネットワーク DTC アクセス**
  - **リモート クライアントを許可します。** 
  - **受信を許可する** 
  - **送信を許可する** 
  - **必要ない Authetnication**
  
4.  **[OK]** を選択して変更を保存します。  
  
5.  MSDTC サービスを再起動するのには、メッセージが表示されたら、選択**はい**です。 MSDTC サービスを再起動した後は、プロパティとコンポーネント サービス MMC を閉じます。 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>MSDTC を Windows ファイアウォールの例外リストに追加します。  

> [!TIP] 
>  Microsoft 分散 Tansaction コーディネーター (MSDTC) は、ファイアウォールで既にできる場合があります。 その場合は、受信の規則として表示されます。 表示されない場合は、このセクションを使用して、MSDTC を許可します。 

1.  開いている**Windows ファイアウォール**を選択し、**詳細設定**左側です。  

    または、**サーバー マネージャー****ツール**、し、**セキュリティが強化された Windows ファイアウォール**です。  
  
2.  右クリックして**受信の規則**を選択して**新しいルール**です。  
  
3.  ウィザード。 

    1. 選択**プログラム**を選択して**次**です。 
    2. 設定、**プログラムのパス**に`%SystemRoot%\system32\msdtc.exe`を選択し、**次**です。  
    3. **接続を許可する**を選択して**次**です。
    4. 選択**ドメイン**を選択して**次**です。
    5. など、任意の名前を入力`MSDTC for Oracle EBS`を選択して**完了**です。
  
5.  ウィザードを完了し、Windows ファイアウォールを閉じます。 
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)