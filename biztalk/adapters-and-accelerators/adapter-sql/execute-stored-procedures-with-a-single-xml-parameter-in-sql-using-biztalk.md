---
title: BizTalk Server を使用して SQL Server での XML パラメーターを 1 つのストアド プロシージャの実行 |Microsoft Docs
description: Biztalk WCF カスタム ポートと SQL アダプタを使用してストアド プロシージャで 1 つのパラメーターを渡す
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a71ee5be554393db10e65adb49694e7104bb011b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976925"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server での XML パラメーターを 1 つのストアド プロシージャを実行します。
1 つのパラメーターを受け取るストアド プロシージャを実行するは」の説明に従って、他のストアド プロシージャの実行に似ています[BizTalk Server を使用して SQL Server でのストアド プロシージャの実行](execute-stored-procedures-in-sql-server-using-biztalk-server.md)します。 ただし、上記のリンクで説明されているアプローチのデザイン時にストアド プロシージャのメタデータを生成し、実行時に、プロシージャを呼び出すオーケストレーションを作成する必要があります。  
  
 その値に対して、処理を実行せずにストアド プロシージャを 1 つ 1 つの値を渡すだけする場所のシナリオを検討してください。 このような場合、メタデータの生成、オーケストレーションを作成、オーケストレーションを展開して、操作の実行のオーバーヘッドは必要ありません。 代わりに、ストアド プロシージャを直接起動するには、Wcf-custom または WCF-SQL 送信ポートを構成できます。 このトピックを使用してこれらのタスクを実行する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  このトピックでは、Wcf-custom を構成する方法についての送信ポートを 1 つのパラメーターを受け取るストアド プロシージャの実行を提供します。 WCF SQL ポートを構成することで、同じ手順を実行できます。 WCF SQL ポートを構成する方法の詳細については、次を参照してください。 [WCF-SQL アダプターを使用してポートを構成する](configure-a-port-using-the-wcf-sql-adapter.md)します。  
  
## <a name="invoke-stored-procedures-without-orchestration"></a>指揮なしのストアド プロシージャを呼び出す  
 オーケストレーションなしの 1 つのパラメーターを使用したストアド プロシージャを実行する方法を説明するためには、このトピックでは、ADD_LAST_EMP_XML_INFO ストアド プロシージャを使用します。 この手順を XML 値をパラメーターとして受け取りに挿入します、**アドレス**の列、**従業員**テーブル。 ストアド プロシージャに渡す XML 値が必要です。 ただし、アダプターを使用してストアド プロシージャを実行するには、プロシージャのスキーマに準拠した要求メッセージを送信する必要があります、値、XML が含まれる、**アドレス**フィールドでは、SQL Server にします。 そのため、によってその要求メッセージを作成する必要があります。  
  
- 使用して、**テンプレート**メッセージ テンプレートを使用して要求メッセージを作成することができますを使用して送信ポートの構成オプション。  
  
- 値、xml、**アドレス**フィールドをメッセージにします。  
  
  これらすべての手順については、このトピックで詳しく説明します。 次の一連のタスクを実行する必要があります。  
  
1. ファイルを作成する受信ポートに挿入される XML ファイルをドロップする場所、**アドレス**の XML フィールド、**従業員**テーブル。 このポートを呼び出すと**MessageIn**ポート。  
  
2. XML ファイルは、ファイルから取得受信ポート、メッセージ テンプレートを使用して、メッセージを作成、ストアド プロシージャを実行する SQL Server に送信します Wcf-custom の一方向の送信ポートを作成します。  
  
   Wcf-custom を構成する手順については、メッセージ テンプレートを使用してポートを送信、トピックのこの部分を提供します。  
  
> [!NOTE]
>  場合でも、このトピックの情報は、1 つの XML パラメーターでストアド プロシージャを実行する方法を示します、任意のデータ型の 1 つのパラメーターを受け取るすべての操作を実行するタスクを実行できます。 唯一の違いは、特定の操作のメッセージ テンプレートを作成する方法になります。 メッセージ テンプレートを作成するには、操作の実行を使用して要求メッセージを取得して、オーケストレーションを使用して、パラメーターの値に置き換えて、BizTalk メッセージ本文。  
  
##  <a name="BKMK_OneWay"></a> Wcf-custom 送信ポートを構成します。  
 WCF カスタムを作成する前に、送信ポート、ファイルを作成することを確認の受信ポート、 **MessageIn**します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
4. 右クリックして**送信ポート**、 をポイント**新規**、順にポイント**静的な一方向送信ポート**します。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. すべてを受信するポートを構成ファイルで破棄されたメッセージの受信ポート、 **MessageIn**します。  
  
   1.  **送信ポートのプロパティ** ダイアログ ボックスで、左側のウィンドウからクリックして**フィルター**します。  
  
   2.  右側のウィンドウで 、**プロパティ**列では、グリッドをクリックし、 **BTS します。ReceivePortName**プロパティ。  
  
   3.  **演算子**列で、"**==**"。  
  
   4.  **値**列で、指定のファイルの名前の受信ポート、 `MessageIn`。  
  
7. **送信ポートのプロパティ** ダイアログ ボックスの 、**全般** タブから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。  
  
8. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。 たとえば、ADD_LAST_EMP_XML_INFO を呼び出すアクションを示します。  
  
      ```  
      Procedure/dbo/ADD_LAST_EMP_XML_INFO  
      ```  
  
   3. をクリックして、**バインド**] タブとの間、**バインドの種類**一覧で、[ **sqlBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
   4. をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
          > [!NOTE]
          >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。  
  
      -   選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  
  
           BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。
  
   5. をクリックして、**メッセージ** タブで、および、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。  
  
   6. **XML**テキスト ボックスに、WCF メッセージの構築に使用されるテンプレートを指定します。 これにより、WCF ベースの ADD_LAST_EMP_XML_INFO 操作に準拠したメッセージを作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
       ![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")  
  
       ADD_LAST_EMP_XML_INFO ストアド プロシージャで、次のテンプレートを指定する必要があります。  
  
      ```  
      <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
      <xml_info>  
      <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
      </xml_info>  
      </ADD_LAST_EMP_XML_INFO>  
      ```  
  
      > [!IMPORTANT]
      >  メッセージ テンプレートでのエンコードと、"string"の送信ポートを使用して呼び出される操作のパラメーターの種類に関係なく常にある必要があります。 たとえば、ADD_LAST_EMP_XML_INFO は、XML 型のパラメーターを受け取りますが、文字列は、メッセージのテンプレートでのエンコードします。  
      > 
      > [!NOTE]
      >  ストアド プロシージャの要求メッセージをコピーして、< xml_info > タグ内の値に置き換えて、BizTalk メッセージ本文では、このメッセージ テンプレートを作成できます。 使用してプロシージャのスキーマを生成することによって、ストアド プロシージャの要求メッセージを取得できます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、要求の XML を取得するスキーマのインスタンスを生成します。  
  
   7. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**します。  
  
10. **送信パイプライン**に対応するパイプラインを選択リストで、 **PassThruTransmit**します。  
  
11. **[OK]** をクリックします。  
  
## <a name="start-the-application"></a>アプリケーションを起動します  
 BizTalk アプリケーションを開始するには、両方のファイルを開始する受信場所と、Wcf-custom 送信ポートを個別にします。 これで、受信場所のファイルにマップされているフォルダーに XML ファイルをコピーする必要があります。 BizTalk アプリケーションが、ファイルを使用して、XML 値は、Employee テーブルの [アドレス] 列に挿入されます。 これは、SQL Server クライアントを使用して、Employee テーブルからレコードを選択して確認できます。  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a>双方向の Wcf-custom 送信ポートを使用します。  
 このトピックで、セクションの指示[Wcf-custom 送信ポートを構成する方法](../../core/how-to-configure-a-wcf-custom-send-port.md)BizTalk を使用しなくても 1 つのパラメーターを持つストアド プロシージャを実行する一方向の Wcf-custom 送信ポートを構成する方法を示しますオーケストレーションです。 ただし、このような場合は、ストアド プロシージャを実行するかどうかを確認する正常にする必要がある SQL Server データベースの Employee テーブルの [アドレス] 列が更新されるかどうかを確認します。  
  
 代わりに、ストアド プロシージャが正常に実行される場合も SQL Server からの応答を取得する双方向の Wcf-custom 送信ポートを作成することができます。 双方向の WCF カスタム ポートを作成する場合、いくつか追加の手順を実行する必要があります。 ファイルが必要がありますに注意してくださいでは、上記の手順で説明したように、場所が表示されます。  
  
1. たとえば、双方向の Wcf-custom 送信ポートを作成**ExecProcedure**します。 送信ポートを構成する手順は、一方向の送信ポートの場合と似ています。 唯一の違いは、双方向のポートにする必要がありますも指定する受信パイプラインです。 選択するかどうかを確認**PassThruReceive**受信パイプラインの。  
  
2. ファイル送信ポートを作成します。 フォルダーに SQL Server データベースから、このポートは、応答メッセージをドロップします。 使用して、**フィルター**  タブのポートのプロパティ ダイアログ ボックスで、Wcf-custom 送信ポートからすべての応答メッセージを受信する FILE 送信ポートを構成します。  
  
   1.  **送信ポートのプロパティ** ダイアログ ボックスで、左側のウィンドウからクリックして**フィルター**します。  
  
   2.  右側のウィンドウで 、**プロパティ**列では、グリッドをクリックし、 **BTS します。SPName**プロパティ。  
  
   3.  **演算子**列で、"**==**"。  
  
   4.  **値**列で、送信ポートの WCF カスタムの名前を指定`ExecProcedure`します。  
  
   3 つすべてのポートを開始します。 コピーをファイルにマップされているフォルダーに XML ファイルの受信場所。 FILE 送信ポートにマップされたフォルダー内の応答を参照してください。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)