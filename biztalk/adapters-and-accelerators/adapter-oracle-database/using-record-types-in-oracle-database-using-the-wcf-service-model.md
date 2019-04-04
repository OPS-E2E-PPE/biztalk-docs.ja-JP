---
title: WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd9bda9fc560310a882c5d48117cd823d544453
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004475"
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行します。
Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。 WCF サービス モデルでは、レコードの種類が厳密に型指定された .NET クラスに逆シリアル化します。 レコードのフィールドは、クラスのプロパティとして表されます。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の種類のレコードの種類をサポートしています。  
  
- ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。  
  
- たとえば、PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類 `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`  
  
- 入れ子になったレコードを含むレコードの種類。  
  
- OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。  
  
- 関数の戻り値であるレコードの種類。  
  
  このトピックでは、WCF サービス モデルでのレコードの種類の表示方法を示します。 Oracle プロシージャと関数を呼び出す方法については、[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)を参照してください。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、SCOTT/ACCOUNT_PKG Oracle の PL/SQL パッケージを使用します。 ACCOUNT_PKG から、次の要素が使用されます。  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 このパッケージを生成するスクリプトが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。 詳細については、スクリプトを参照してください。  
  
 サンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  
  
## <a name="record-types-in-the-wcf-service-model"></a>WCF サービス モデル内のレコードの種類  
 Oracle のレコードの種類は、複雑な XML 型として表されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 WCF サービス モデルで複雑な XML 型が、クラスによって表され、このクラスのプロパティは、Oracle のレコードの種類のフィールドを表します。 レコード型のパラメーターを表すクラスは、関数またはプロシージャのスキーマとパッケージ (ある場合) に限定されている名前空間に生成されます。 この名前空間には、関数またはプロシージャ パラメーターの一意に識別します。 次の名前空間での Oracle パッケージの ACCOUNT_PKG CREATE_ACCOUNT プロシージャにレコードの型パラメーターを作成するなど。`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`します。 プロシージャおよび関数での複合型を表すために WCF サービス モデルで使用する名前空間の詳細については、[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)を参照してください。  
  
 レコード型のパラメーターの名前空間は、プロシージャまたは関数によって決まりますが、レコードの種類が宣言されているレコードの型パラメーターに対して生成されたクラスの名前がところで決定されます。 次の表は、Oracle のレコードの型パラメーターを宣言することの 2 つの方法に基づいて、クラスの名前を生成する方法を示します。  
  
|Oracle のレコードの種類|名前|例|  
|------------------------|----------|-------------|  
|テーブル %rowtype のプロシージャまたは関数のパラメーター|[パラメーター名]レコード|ACCTRECORD|  
|レコードのパッケージのパラメーターの型|[PACKAGE_NAME][RECORD_TYPE_NAME]レコード|ACCOUNT_PKGACCTINFO_REC_TYPERECORD|  
  
 [パラメーター名]; プロシージャまたは関数のパラメーターの名前を =たとえば、アカウント  
  
 [PACKAGE_NAME] = Oracle パッケージの名前。  
  
 [RECORD_TYPE_NAME]; レコードの種類の宣言で指定された名前を =たとえば、ACCTINFO_REC_TYPE です。  
  
 次のコードでは、2 つの Oracle 関数に対して生成された WCF クライアントのメソッド シグネチャを示します。 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 関数は 2 つ単純なレコードで、型パラメーターを受け取り、/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO 関数が入れ子になった 2 つのレコード型を含むレコードの型パラメーターを返します。 Oracle 関数の宣言は、コードの先頭に含まれています。 各関数のパラメーターは、一意の名前空間によって修飾されます。  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 次のコードは、CREATE_ACCOUNT 関数のパラメーターに対して生成されたクラスを示しています。 `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`  
  
 この関数はテーブル %rowtype で宣言されたパラメーターおよびパッケージの種類のレコード型で宣言パラメーター (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT {  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGADDRESS_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
}  
```  
  
### <a name="representation-of-a-simple-record-type"></a>単純なレコード型の表現  
 次のコードでは、単純なレコードの種類を WCF サービス モデルで表現する方法を示します。 このコードの展開ビューを示しています、 **ACCOUNTRECORD** CREATE_ACCOUNT 関数では、アカウント %rowtype パラメーターを表すクラスです。 このクラスでは、レコードのフィールド (行の列) はプロパティとして表されます。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Runtime.Serialization.DataContractAttribute()]  
public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
    private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
    private System.Nullable<decimal> ACCTIDField;  
  
    private string NAMEField;  
  
    private System.Nullable<decimal> BALANCEField;  
  
    public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
        get {  
            return this.extensionDataField;  
        }  
        set {  
            this.extensionDataField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public System.Nullable<decimal> ACCTID {  
        get {  
            return this.ACCTIDField;  
        }  
        set {  
            this.ACCTIDField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public string NAME {  
        get {  
            return this.NAMEField;  
        }  
        set {  
            this.NAMEField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute(Order=2)]  
    public System.Nullable<decimal> BALANCE {  
        get {  
            return this.BALANCEField;  
        }  
        set {  
            this.BALANCEField = value;  
        }  
    }  
}  
```  
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a>入れ子になったレコードを含むレコード型の表現  
 次のコードでは、入れ子になったレコードを格納するレコード型の表現を示します。 この特定のレコードの種類は GET_ACCOUNTINFO 関数の戻り値 (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`)。 ACCTINFO_REC_TYPE タイプのレコードの構造を使用して宣言されているパッケージのパラメーターは、(`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。 2 つの単純なレコードを入れ子になった型、テーブル % の行のレコードおよびレコードの種類、パッケージが含まれています。 これら 2 つの単純なレコードは、親レコードと同じ名前空間で宣言され、予期される名前付け規則に従ってください。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGACCTINFO_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCTField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESSField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCT {  
            get {  
                return this.ACCTField;  
            }  
            set {  
                this.ACCTField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESS {  
            get {  
                return this.ADDRESSField;  
            }  
            set {  
                this.ADDRESSField = value;  
            }  
        }  
    }  
```  
  
## <a name="using-record-types-in-your-code"></a>コード内のレコードの種類を使用します。  
 レコードの種類を使用して、コードでは簡単です。 レコード型のパラメーターを持つ関数またはプロシージャを呼び出すには、レコード型または型のインスタンスを作成し、WCF クライアントで、適切なメソッドに渡すことです。 プロシージャまたは関数から返される任意の出力のプロパティを読み取ることができます、IN OUT パラメーターまたは関数の戻り値または場合は、レコードの種類として宣言されます。 WCF サービス モデルを使用してプロシージャと関数を呼び出す方法の詳細については、[関数を呼び出すと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)を参照してください。  
  
> [!IMPORTANT]
>  Oracle のレコード型のパラメーター (と関数の戻り値) は、その関数またはプロシージャ (、およびパッケージ) の名前空間によって修飾されます。 これは、2 つの別のプロシージャまたは関数で使用されているレコードの種類が各プロシージャまたは関数の別の名前空間にあることを意味します。 特定のプロシージャまたは関数を使用する場合は、レコードの種類を正しく修飾するためを確認する必要があります。 たとえば、パッケージに 2 つの異なる関数を IN パラメーターとして使用されるレコードの種類 (レコードの種類の宣言) が各関数に対して生成された一意の名前空間に対応する各宣言に WCF クライアント コードで 2 回宣言されます。 それぞれの各関数に渡すパラメーターで、正しい名前空間を使用することを確認する必要があります。  
  
 次の例では、2 つの単純なレコード パラメーター CREATE_ACCOUNT 関数が呼び出されます。 次に、GET_ACCOUNTINFO 関数が呼び出されます。 この関数は、入れ子になったレコードを含むレコードの種類を返します。 選択したフィールドが、返されるレコードの値は、コンソールに書き込まれます。 手順を実行する Oracle データベースの資格情報を設定し、WCF クライアントを開くには、この例から省略されます。  
  
```  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
…  
  
// Create the client from configuration  
using (SCOTTPackageACCOUNT_PKGClient accountPkgClient = new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG"))  
{  
  
    ...  
  
    decimal acctId;  
  
    // Create an account record  
    // Note: ACCTRECORD is defined in both namespaces so specify the definition  
    // that corresponds to the client.  
  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD acctRec =   
        new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD();  
  
    // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
    acctRec.ACCTID = 0;  
    acctRec.NAME = "Anton Kirilov";  
    acctRec.BALANCE = 9583;  
  
    // Create address record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
    addrRec.STREET = "234 Main St";  
    addrRec.CITY = "Boston";  
    addrRec.STATE = "MA";  
  
    // Create account  
    try  
    {  
        acctId = (decimal)accountPkgClient.CREATE_ACCOUNT(acctRec, addrRec);  
    }  
    catch (Exception ex)  
    {  
        // handle exception  
        ...  
    }  
  
    ...  
  
    // Account info record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD acctInfo =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD();  
  
    // Get account info for the account just created  
    // acctInfo is returned as a nested record type  
    try  
    {  
     acctInfo = accountPkgClient.GET_ACCOUNTINFO(acctId);  
    }  
    catch (Exception ex)  
    {  
    // handle exception  
    ...  
    }  
  
    // Write the account info to the console  
    Console.WriteLine("The account info is:");  
    Console.WriteLine("Name:\t\t\t{0}", acctInfo.ACCT.NAME);  
    Console.WriteLine("Street:\t\t\t{0}", acctInfo.ADDRESS.STREET);  
    Console.WriteLine("City:\t\t\t{0}", acctInfo.ADDRESS.CITY);  
    Console.WriteLine("State:\t\t\t{0}", acctInfo.ADDRESS.STATE);  
    Console.WriteLine("Account Id:\t\t{0}", acctInfo.ACCT.ACCTID);  
    Console.WriteLine("Account Balance:\t{0:C}", acctInfo.ACCT.BALANCE);  
  
    Console.WriteLine("\nHit <RETURN> to finish");  
    Console.ReadLine();  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)