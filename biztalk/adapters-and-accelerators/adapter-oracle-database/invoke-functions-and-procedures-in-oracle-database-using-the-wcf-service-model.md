---
title: "関数と、WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a6256491100939937113ac6f140adc031da0941
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a>関数と、WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]プロシージャ、関数、およびパッケージの操作を表示します。 WCF サービス モデルでは、これらの操作は、WCF クライアントのメソッドとして表されます。 WCF サービス モデルと[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   **関数がサポートされて**です。 Oracle 関数の戻り値は、WCF クライアント メソッドの戻り値として確認できます。 Oracle パラメーターは、WCF クライアント メソッドに (適切な方向と定義されている以下) のパラメーターとして表示されます。  
  
-   **プロシージャがサポート**です。 最初の出力、Oracle プロシージャのパラメーターは、WCF クライアント メソッドの戻り値として確認できます。 その他のすべての Oracle パラメーターは、WCF クライアント メソッドに (適切な方向と定義されている以下) のパラメーターとして表示されます。  
  
-   **Oracle パッケージをサポート**です。 パッケージの名前は、操作の名前とそのパラメーターの型の名前空間が修飾されます。  
  
-   **サポートには、関数およびプロシージャがオーバー ロードされた**です。  
  
-   **サポート IN、OUT とプロシージャおよび関数の両方の基本の Oracle データ型のパラメーターを IN**です。 OUT パラメーターとして表示された**アウト**WCF クライアント メソッドのパラメーターとで OUT パラメーターとして表示された**ref**パラメーター。  
  
-   **サポート IN、OUT、および IN OUT プロシージャと関数、関数の戻り値の REF CURSOR パラメーター**です。 詳細については、次を参照してください。[を実行する操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)です。  
  
-   **サポートは、OUT、IN OUT レコード プロシージャや関数のパラメーターの型し関数の戻り値**です。 詳細については、次を参照してください。[を実行する操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの使用、/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT の例では、プロシージャがオーバー ロードされます。 この手順では、アカウント ID またはアカウント名のいずれかに基づいて、SCOTT/アカウント テーブルからレコードを読み取ります。 この手順と表を生成するスクリプトは、SDK サンプルの値が提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 次の表は、WCF クライアントと手順については、生成されたメソッドの名前が機能し、パッケージであり、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスします。 関数またはプロシージャをオーバー ロードする場合を除き、1 つの WCF クライアントを使用して、すべてのスキーマのすべてのスキーマでプロシージャまたは関数のすべての機能およびパッケージ内のプロシージャを呼び出します。  
  
|Oracle の成果物|WCF クライアントの操作名|例|  
|---------------------|-------------------------------|-------------|  
|手順|[スキーマ]ProcedureClient です。[PROC_NAME]|SCOTTProcedureClient.MYPROC|  
|関数|[スキーマ]FunctionClient です。[FUNC_NAME]|SCOTTProcedureClient.MYFUNC|  
|パッケージ (プロシージャまたは関数)|[スキーマ]パッケージ [PACKAGE_NAME] のクライアントです。[PROC_NAME または FUNC_NAME]|SCOTTPackageMYPACKAGEClient.MYPROC|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [PROC_NAME];、Oracle のプロシージャの名前を =たとえば、MYPROC です。  
  
 [FUNC_NAME]、Oracle 関数の名前を =たとえば、MYFUNC です。  
  
 [PACKAGE_NAME] = Oracle パッケージの名前。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーターを入力および Oracle のレコードの行のデータ (またはフィールド) を含む複雑な XML 型としての REF CURSOR パラメーターによって返される結果セットだけでなく、値を返す Oracle レコードを表します。 .NET クラスとして表されるこれらの XML 型の各モデルでは、WCF サービス、クラスのプロパティは、レコード型または REF カーソルの結果セットのフィールドを表します。 Oracle のレコードの種類は、厳密に型指定された .NET クラスとして常に表されます。 ただし、REF CURSOR の結果セットは、自体 REF カーソルが宣言されていると厳密に型指定または厳密に型指定されたかどうかに基づいて厳密に型指定されたか、弱い型指定のレコードとして表現できます。 表す REF CURSOR またはレコード型のパラメーター (または戻り値) は、プロシージャ、関数、またはパッケージに基づく一意の名前空間で生成されるクラスです。 次の表は、これらの名前空間を示します。  
  
|Oracle の成果物|名前空間|例|  
|---------------------|---------------|-------------|  
|手順|[BASE_NS] です。 [スキーマ] です。プロシージャです。[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Procedure.MYPROC|  
|関数|[BASE_NS] です。 [スキーマ] です。関数。[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Function.MYFUNC|  
|パッケージ (プロシージャ)|[BASE_NS] です。 [スキーマ] です。パッケージです。[PACKAGE_NAME] です。[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYPROC|  
|パッケージ (Function)|[BASE_NS] です。 [スキーマ] です。パッケージです。[PACKAGE_NAME] です。[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYFUNC|  
|汎用レコードに設定 (弱い型指定)|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = ベース アダプターの名前空間です。microsoft.lobservices.oracledb._2007._03 です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。  
  
 [FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。  
  
 [PACKAGE_NAME] = Oracle パッケージの名前。  
  
 レコードのパラメーターをこれらの名前空間を使用する方法については、次を参照してください。[を実行する操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)です。 REF CURSOR パラメーターをこれらの名前空間を使用する方法については、次を参照してください。[を実行する操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)です。  
  
 一般に、Oracle パラメーターと戻り値でマップされたとおり、WCF クライアント メソッド。  
  
-   Oracle IN パラメーターは、.NET (入力) パラメーターにマップされます。  
  
-   .NET に oracle OUT パラメーターを割り当てる**アウト**パラメーター。  
  
-   .NET に oracle IN OUT パラメーターを割り当てる**ref**パラメーター。  
  
-   関数の戻り値は、メソッドの戻り値にマップされます。  
  
 ただし、2 つの重要な例外があります。  
  
-   REF CURSOR を oracle IN パラメーターが入力文字列と、出力に分割されます (**アウト**) セットを記録します。 これは、ため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN REF CUSROR パラメーターを表すこれら、文字列、複合型 (レコード セット) としての REF CURSOR 出力パラメーターとして 1 つのパラメーターに組み合わせることはできません。  
  
-   最初の出力パラメーター、Oracle のプロシージャでは、WCF クライアント メソッドの戻り値にマップされます。 これは、標準の WCF 動作です。  
  
 次の例では、単純な Oracle プロシージャ (SCOTT スキーマに読み込まれる) の一部とそれを呼び出すために生成される WCF クライアント メソッドのシグネチャを示します。 Oracle プロシージャには、3 個の IN パラメーター、3 つの OUT パラメーター、および 3 OUT パラメーターです。ただし、WCF クライアントのメソッドは、最初の出力パラメーターのパラメーターをマップできません。 代わりにメソッドの戻り値にマップされます。  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a>オーバー ロードされたプロシージャ、関数、およびパッケージのサポート  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポートしていますが、ノード ID と名前空間をオーバー ロードされた各成果物を表示する一意の文字列を追加することによってプロシージャ、関数、およびパッケージをオーバー ロードされました。 この文字列は、次のオーバー ロードの最初のオーバー ロード"overload2"の"overload1"がします。  
  
 WCF サービス モデルの各オーバー ロードされたプロシージャまたは関数は、一意の WCF クライアントで表されます。 これとは異なるスキーマでプロシージャのすべてのスキーマ内の関数のすべてのオーバー ロードされた非ケースまたはのプロシージャと、パッケージ内の関数はすべて、同じ WCF クライアントによって呼び出されます。 次の表は、名、およびメソッドのオーバー ロードされたプロシージャ、関数、およびパッケージの生成、WCF クライアントを示します。  
  
|Oracle の成果物|WCF クライアント名|例|  
|---------------------|---------------------|-------------|  
|オーバー ロードされたパッケージ (プロシージャ)|[スキーマ]パッケージの [PACKAGE_NAME] [PROC_NAME] [OVERLOAD_ID] のクライアントです。[PROC_NAME]|SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC|  
|オーバー ロードされたパッケージ (Function)|[スキーマ]パッケージの [PACKAGE_NAME] [FUNC_NAME] [OVERLOAD_ID] のクライアントです。[FUNC_NAME]|SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。  
  
 [FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。  
  
 [PACKAGE_NAME] = Oracle パッケージの名前。  
  
 [OVERLOAD_ID]; オーバー ロードされた成果物を識別する一意の文字列を ="overload1"、"overload2"、およびなどです。  
  
 次の表は、オーバー ロードされたプロシージャ、関数、およびパッケージの生成された名前空間を示します。  
  
|Oracle の成果物|名前空間|例|  
|---------------------|---------------|-------------|  
|パッケージ (プロシージャ)|[BASE_NS] です。 [スキーマ] です。パッケージです。[PACKAGE_NAME] です。[PROC_NAME][OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYPROC.overload1|  
|パッケージ (Function)|[BASE_NS] です。 [スキーマ] です。パッケージです。[PACKAGE_NAME] です。[FUNC_NAME] です。[OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYFUNC.overload1|  
|汎用レコードに設定 (弱い型指定)|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = ベース アダプターの名前空間です。microsoft.lobservices.oracledb._2007._03 です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。  
  
 [FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。  
  
 [PACKAGE_NAME] = Oracle パッケージの名前。  
  
 [OVERLOAD_ID]; オーバー ロードされた成果物を識別する一意の文字列を ="overload1"、"overload2"、およびなどです。 文字列内の数値は、Oracle データベースで保持されている成果物のオーバー ロードの ID です。  
  
 次の例では、WCF クライアントと ACCOUNT_PKG パッケージ内のオーバー ロードされた GET_ACCOUNT プロシージャについて生成されたメソッドのシグネチャを示します。 (Oracle の宣言が含まれます) です。この例では、各オーバー ロードの一意の WCF クライアントを生成する方法と、クライアントごとに生成されたメソッドが一意の名前空間のレコード セットを返す方法を示します。  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a>呼び出し元関数およびプロシージャ  
 WCF クライアントを使用して、関数またはプロシージャを呼び出すには、次の手順を実行します。  
  
1.  対象とする関数、プロシージャ、またはパッケージの WCF クライアント クラスを生成します。 このクラスは、ターゲットの成果物に呼び出すことができる操作のメソッドを含める必要があります。  
  
    > [!NOTE]
    >  [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、オーバー ロードされた関数およびプロシージャに表示されます、**利用可能なカテゴリと操作**[name].1、.2、.3 の [名前] の [名前] ボックスに、[NAME] はオーバー ロードされた成果物と数値の値の名前を指定Oracle データベースでオーバー ロードの ID です。  
  
2.  WCF クライアント クラスのインスタンスを作成し、関数またはプロシージャを呼び出すには、そのメソッドを呼び出します。  
  
 詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。  
  
> [!IMPORTANT]
>  関数またはプロシージャ (およびパッケージ) の値を返しますまたは REF CURSOR およびレコードの型パラメーターを表すクラスは、関数またはプロシージャごとに一意の名前空間でも宣言されます。 つまり、たとえば、WCF クライアントのメソッドごとに異なる 2 つの関数の戻り値として使用されているパッケージ REF カーソルの種類が一意の名前空間で宣言されます。 これらの異なる値を返すか、WCF クライアントのいずれかを呼び出すときに変数を適切にキャストを保持するために別々 の変数を宣言する必要がありますか。  
  
 次の例では、/SCOTT/ACCOUNT テーブルからアカウント レコードを取得するオーバー ロードされた/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT プロシージャを呼び出すことを示します。 まず、/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT プロシージャを呼び出すことによって、新しいレコードが作成されます。 新しいレコードが読み込まれる GET_ACCOUNT のさまざまなオーバー ロードを呼び出すことによって、2 回バックアップします。 この例では、3 つの WCF クライアント、CREATE_ACCOUNT プロシージャと 1 つ各 GET_ACCOUNT いずれのオーバー ロードを使用します。 エイリアスは、GET_ACCOUNT の戻り値を使用する名前空間を区別するために使用されます。 フル サンプルは、SDK サンプルで使用します。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)