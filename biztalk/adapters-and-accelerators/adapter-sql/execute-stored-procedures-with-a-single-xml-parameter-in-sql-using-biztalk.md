---
title: "BizTalk Server を使用して SQL Server で 1 つの XML パラメーターを持つストアド プロシージャを実行 |Microsoft ドキュメント"
description: "Biztalk WCF カスタム ポートと SQL アダプタを使用してストアド プロシージャで 1 つのパラメーターを渡す"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02c5f239300140022b1d26f35664add744b630c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server で 1 つの XML パラメーターを持つストアド プロシージャを実行します。
」の説明に従って、他のストアド プロシージャの実行に似ていますが、1 つのパラメーターを受け取るストアド プロシージャを実行する[BizTalk Server を使用して SQL Server でストアド プロシージャの実行](execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。 ただし、上記のリンクで説明されているアプローチのデザイン時にストアド プロシージャのメタデータを生成し、実行時にプロシージャを呼び出すオーケストレーションを作成する必要があります。  
  
 その値の処理を行わず、ストアド プロシージャに 1 つの 1 つの値を渡すだけする場所のシナリオを検討してください。 このような場合に、メタデータの生成、オーケストレーションを作成、オーケストレーションを展開して、操作を実行するのオーバーヘッドがしません。 代わりに、直接、ストアド プロシージャを呼び出すには、Wcf-custom または WCF-SQL 送信ポートを構成できます。 このトピックは、これらのタスクを実行する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  このトピックでは、Wcf-custom を構成する方法についての送信を 1 つのパラメーターを受け取るストアド プロシージャを実行するためのポートを提供します。 同じ手順を実行するには、WCF SQL ポートを構成します。 WCF SQL ポートの構成方法の詳細については、次を参照してください。 [WCF-SQL アダプターを使用してポートを構成する](configure-a-port-using-the-wcf-sql-adapter.md)です。  
  
## <a name="invoke-stored-procedures-without-orchestration"></a>指揮なしのストアド プロシージャを呼び出す  
 せず、オーケストレーションの単一のパラメーターを使用してストアド プロシージャを実行する方法を示すためには、このトピックは ADD_LAST_EMP_XML_INFO ストアド プロシージャを使用します。 この手順は、パラメーターとして XML 値を取得しに挿入、**アドレス**の列、**従業員**テーブル。 ストアド プロシージャに渡す XML 値が必要です。 ただし、アダプターを使用してストアド プロシージャを実行するには、プロシージャのスキーマに準拠した要求メッセージを送信する必要があります、値を XML を含む、**アドレス**フィールドでは、SQL Server にします。 そのため、によってその要求メッセージを作成する必要があります。  
  
-   使用して、**テンプレート**メッセージ テンプレートを使用して要求メッセージを作成することができますを使用して送信ポートの構成オプション。  
  
-   値、xml、**アドレス**フィールドをメッセージにします。  
  
 これらすべての手順については、このトピックで詳しく説明します。 次の一連のタスクを実行する必要があります。  
  
1.  ファイルを作成する受信ポートに挿入される XML ファイルをドロップする場所、**アドレス**XML フィールドの**従業員**テーブル。 このポートを呼び出すと**MessageIn**ポートです。  
  
2.  XML ファイルは、ファイルから取得の受信ポート、メッセージ テンプレートを使用して、メッセージを作成、ストアド プロシージャを実行する SQL Server に送信 Wcf-custom 一方向の送信ポートを作成します。  
  
 トピックのこの部分では、Wcf-custom を構成する手順についての送信ポート、メッセージのテンプレートを提供します。  
  
> [!NOTE]
>  このトピックの情報は、XML パラメーターを 1 つのストアド プロシージャを実行する方法を示します、場合でもは、任意のデータ型の 1 つのパラメーターを受け取るすべての操作を実行するタスクを実行できます。 唯一の違いは、特定の操作についてメッセージ テンプレートを作成する方法になります。 メッセージ テンプレートを作成するには、操作を実行するを使用する要求メッセージを実行して、オーケストレーションを使用して、パラメーターの値に置き換えて、BizTalk メッセージ本文。  
  
##  <a name="BKMK_OneWay"></a>Wcf-custom 送信ポートを構成します。  
 WCF カスタムを作成する前に、送信ポート、ファイルを作成することを確認の受信ポート、 **MessageIn**です。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
4.  右クリック**送信ポート**、指す**新規**、順にポイントし、**静的な一方向送信ポート**です。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  すべてを受信するポートを構成ファイルで破棄されたメッセージの受信ポート、 **MessageIn**です。  
  
    1.  **送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**フィルター**です。  
  
    2.  右側のペインで下にある、**プロパティ**列では、グリッドをクリックし、 **BTS です。ReceivePortName**プロパティです。  
  
    3.  **演算子**列で、"**==**"です。  
  
    4.  **値**列で、受信ポートのファイルの名前を指定して`MessageIn`です。  
  
7.  **送信ポートのプロパティ**ダイアログ ボックスの**全般** タブから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリック**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)**フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧についてはします。 たとえば、ADD_LAST_EMP_XML_INFO を呼び出すアクションを示します。  
  
        ```  
        Procedure/dbo/ADD_LAST_EMP_XML_INFO  
        ```  
  
    3.  クリックして、**バインド**] タブとの間、**バインディングの種類**一覧で、[ **sqlBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
    4.  クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名を指定とパスワードを SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
            > [!NOTE]
            >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。  
  
        -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
             BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。
  
    5.  クリックして、**メッセージ**] タブで、し、[、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。  
  
    6.  **XML**テキスト ボックスで、WCF メッセージを構築するために使用されるテンプレートを指定します。 これにより、WCF ベース ADD_LAST_EMP_XML_INFO 操作に準拠したメッセージを作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
         ![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")  
  
         ADD_LAST_EMP_XML_INFO ストアド プロシージャの次のテンプレートを指定する必要があります。  
  
        ```  
        <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
        <xml_info>  
        <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
        </xml_info>  
        </ADD_LAST_EMP_XML_INFO>  
        ```  
  
        > [!IMPORTANT]
        >  メッセージ テンプレートでのエンコードと、"string"送信ポートを使用して呼び出される操作のパラメーターの型に関係なく常にする必要があります。 たとえば、ADD_LAST_EMP_XML_INFO は、XML 型のパラメーターを受け取りますが、文字列は、メッセージのテンプレートでのエンコーディングします。  
  
        > [!NOTE]
        >  このメッセージのテンプレートを作成するにはストアド プロシージャの要求メッセージをコピーして、BizTalk メッセージ本文 < xml_info > タグ内で値を置換します。 使用して、プロシージャのスキーマを生成することによって、ストアド プロシージャの要求メッセージを取得できます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、および XML 要求を取得するスキーマのインスタンスを生成します。  
  
    7.  戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**です。  
  
10. **送信パイプライン**一覧に対応するパイプラインを選択して**PassThruTransmit**です。  
  
11. **[OK]**をクリックします。  
  
## <a name="start-the-application"></a>アプリケーションを開始します。  
 BizTalk アプリケーションを起動するには、両方のファイルを開始する場所を受信し、Wcf-custom 送信ポートが個別にします。 必要があります。 受信場所がファイルにマップされているフォルダーに XML ファイルをコピーします。 BizTalk アプリケーションが、ファイルを使用し、XML 値は、Employee テーブルの [アドレス] 列に挿入されます。 これは、SQL Server クライアントを使用して、従業員テーブルからレコードを選択して確認できます。  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a>双方向の Wcf-custom 送信ポートを使用します。  
 セクションの下のこのトピックの手順に[Wcf-custom 送信ポートを構成する方法](../../core/how-to-configure-a-wcf-custom-send-port.md)BizTalk を使用しなくても 1 つのパラメーターを持つストアド プロシージャを実行する一方向の Wcf-custom 送信ポートを構成する方法を示しますオーケストレーションです。 ただし、このような場合は、ストアド プロシージャが実行されたかどうかを確認が正常にする必要がある SQL Server データベースには Employee テーブルの [アドレス] 列を更新するかどうかを確認します。  
  
 代わりに、ストアド プロシージャが正常に実行された場合は、SQL Server から応答も取得する双方向の Wcf-custom 送信ポートを作成することができます。 双方向の WCF カスタム ポートを作成する場合は、いくつかの追加手順を実行する必要があります。 ファイルが必要がありますに注意してくださいでは、上記の手順で説明したようの場所が表示されます。  
  
1.  たとえば、双方向の Wcf-custom 送信ポートを作成する**ExecProcedure**です。 送信ポートを構成する手順は、一方向の送信ポートの場合と似ています。 唯一の違いは、双方向のポートにする必要がありますも指定する、受信パイプラインです。 選択するかどうかを確認**PassThruReceive**受信パイプラインのです。  
  
2.  FILE 送信ポートを作成します。 このポートは、SQL Server データベースからの応答メッセージをフォルダーに削除されます。 使用して、**フィルター**  タブのポートのプロパティ ダイアログ ボックスには、Wcf-custom 送信ポートからすべての応答メッセージを受信する FILE 送信ポートを構成します。  
  
    1.  **送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**フィルター**です。  
  
    2.  右側のペインで下にある、**プロパティ**列では、グリッドをクリックし、 **BTS です。SPName**プロパティです。  
  
    3.  **演算子**列で、"**==**"です。  
  
    4.  **値**列で、送信ポート、WCF カスタムの名前を指定して`ExecProcedure`です。  
  
 3 つすべてのポートを開始します。 受信場所がファイルにマップされているフォルダーに XML ファイルのコピー。 FILE 送信ポートにマップされているフォルダーに応答を探します。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)