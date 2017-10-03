---
title: "WCF サービス モデルを使用して Oracle データベースで操作を使用して REF CURSOR を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb527a4451388475ce69a5321d0d05616fc8afde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行します。
REF CURSOR は、Oracle データベースに結果セットへのポインターを表す Oracle PL/SQL データ型です。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]プロシージャ、関数、およびパッケージ内の REF CURSOR パラメーターをサポートしています。 REF CURSOR パラメーターには、厳密に型指定または厳密に型指定されたプロシージャまたは関数の宣言方法に応じてを指定できます。 REF CURSOR パラメーターを表現する方法の詳細について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[REF CURSOR のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)です。次の表では、WCF サービス モデルでの REF CURSOR パラメーターを表現する方法をまとめたものです。  
  
|パラメーターの方向|厳密に型指定された REF CURSOR|弱い型指定の REF CURSOR|  
|-------------------------|--------------------------------|------------------------------|  
|IN|`string [PARAM_NAME]`<br /><br /> PL/SQL ブロックを含む文字列です。 PL/SQL ブロックは、"オープンの SELECT"ステートメントを実行するか、関数またはプロシージャを呼び出すことによって開かれた REF CURSOR を返す必要があります。 疑問符 (?) では、REF CURSOR を返す、パラメーターの位置を示します。 たとえば、"OPEN を開始しますか。 SELECT * MY_TABLE; から最後に、"または"BEGIN MY_PROC (PARM1、?、PARM2);終了;"です。|厳密に型指定と同じ|  
|OUT|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> 厳密に型指定されたレコード セット。|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> 厳密に型指定されたジェネリック レコード セット。|  
|OUT IN|REF CURSOR 出力パラメーターは、IN、OUT パラメーターに分割されます。 IN パラメーターは、OUT パラメーターと区別するためのメソッド シグネチャで"_IN"に付加されます。 OUT パラメーターは、厳密に型指定されたレコード セットで表されます。<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|REF CURSOR 出力パラメーターは、IN、OUT パラメーターに分割されます。 IN パラメーターには、OUT パラメーターと区別するためには、"_IN"が追加されます。 OUT パラメーターは、弱い型指定のレコード セットで表されます。<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 [PARAM_NAME]、Oracle データベースで関数またはプロシージャの定義でパラメーターの名前を =たとえば、MYREFCURSOR です。  
  
 [PROC_NS] パッケージ、プロシージャ、または関数のパラメーターを含むに生成された一意の名前空間を =たとえば、"microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.ACCOUNT_PKG です。GET_ACTIVITY"です。  
  
 [GENERIC_NS]、ジェネリックのレコード セットが定義されている名前空間を ="microsoft.lobservices.oracledb._2007._03"です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、SCOTT/パッケージ/ACCOUNT_PKG の Oracle パッケージを使用します。 次の手順は ACCOUNT_PKG から使用されます。  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 このパッケージを生成するスクリプトは、SDK サンプルの値が提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a>WCF サービス モデルの REF CURSOR パラメーター  
 次の例では、クラスおよび/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY プロシージャに対して生成される WCF クライアントを表示します。 この手順が弱い型指定に、厳密に型指定された IN OUT REF CURSOR パラメーターや REF CURSOR 出力パラメーターです。  
  
 GET_ACTIVITY を呼び出すために WCF クライアントで生成されるメソッドのシグネチャを次に示します。  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 **GET_ACTIVITY**メソッド、INOUTRECS の 2 つのパラメーターは分割 IN OUT パラメーター。  
  
-   INOUTRECS_IN は、REF CURSOR パラメーターを表す文字列です。  
  
-   INOUTRECS は、REF CURSOR 出力パラメーターを表す厳密に型指定されたレコード セットです。  
  
 厳密に型指定された OUT パラメーター、OUTRECS は、汎用のレコード セットとして表されます。 厳密に型指定されたパラメーター、INRECS には、文字列として表されます。  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a>厳密に型指定された出力 REF CURSOR パラメーター  
 厳密に型指定された出力 (または IN OUT) スキーマ、パッケージ、およびプロシージャまたはそれらを使用する関数の名前に基づく一意の名前空間での REF CURSOR パラメーターが生成されます。 この名前空間は、手順については、/SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`です。 クラス名が「レコード」を持つパラメーターの名前を追加することによって作成され、Oracle フィールドを表すプロパティは、クラスで構成されます。 INOUTRECS REF CURSOR パラメーターに対して生成される厳密に型指定されたレコードを表すクラスの一部を次に示します。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class INOUTRECSRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private System.Nullable<decimal> TIDField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public System.Nullable<decimal> TID {  
            get {  
                return this.TIDField;  
            }  
            set {  
                this.TIDField = value;  
            }  
        }  
  
        ...  
  
    }  
}  
```  
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a>REF CURSOR パラメーターを弱い型指定  
 弱い型指定 IN OUT は OUT (または) の REF CURSOR パラメーターはジェネリック レコード クラスによって表されます。 ジェネリック レコード セットが、同じ名前空間の名前を使用して、同じクラス関数またはプロシージャに関係なく常に生成されます。 次のコードは、ジェネリック レコード クラスには、 **microsoft.lobservices.oracledb._2007._03.GenRecordRow**、OUTRECS アウト SYS_REFCURSOR パラメーター (厳密に型指定された) のレコードを表します。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordRow : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumnField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumn {  
            get {  
                return this.GenRecordColumnField;  
            }  
            set {  
                this.GenRecordColumnField = value;  
            }  
        }  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordColumn : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private string ColumnNameField;  
  
        private string ColumnValueField;  
  
        private string ColumnTypeField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false)]  
        public string ColumnName {  
            get {  
                return this.ColumnNameField;  
            }  
            set {  
                this.ColumnNameField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public string ColumnValue {  
            get {  
                return this.ColumnValueField;  
            }  
            set {  
                this.ColumnValueField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false, Order=2)]  
        public string ColumnType {  
            get {  
                return this.ColumnTypeField;  
            }  
            set {  
                this.ColumnTypeField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a>WCF クライアントで REF カーソル パラメーターの使用  
 WCF クライアントを使用して、プロシージャまたは REF CURSOR パラメーターを持つ関数を呼び出しするには、以下が行います。  
  
1.  それぞれの文字列を渡すまたは REF カーソルをオープンする PL/SQL を含む IN OUT REF CURSOR パラメーターをブロックします。 このブロックでは、開いているステートメントを実行することか、関数または OUT パラメーターで開かれている REF CURSOR を返すプロシージャを呼び出すできます。  
  
2.  プロシージャまたは関数が戻るときに、パラメーター、OUT または REF CURSOR を IN に対して返されるレコード セット内のデータを操作します。 レコード セットは、弱い型指定の REF CURSOR パラメーターのセットの汎用レコードまたは厳密に型指定されたレコードの REF CURSOR パラメーターの厳密に型指定されたセットになります。  
  
 WCF サービス モデルを使用してプロシージャと関数を呼び出す方法の詳細については、次を参照してください。[関数の呼び出しと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)です。  
  
 次の例では、GET_ACTIVITY プロシージャを呼び出します。 REF CURSOR パラメーターを指定するのどちらの方法を示しています。  
  
-   REF CURSOR パラメーター アカウント 100001 活動で返される、開いている用の SELECT ステートメントを指定します。  
  
-   REF CURSOR を IN パラメーター/SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY プロシージャが呼び出されます。 この手順では、ACCOUNTACTIVITY テーブル内のアクティビティのすべてを含み、OUT パラメーターとして返す REF カーソルを開きます。  
  
 この例では、レコード厳密に型指定され、弱い型指定の両方の REF CURSOR パラメーターで返されるセットからデータを読み取る方法も示します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// namespaces for strongly-typed and weakly typed REF CURSOR records  
using GET_ACTIVITYns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY;  
using GENERICns = microsoft.lobservices.oracledb._2007._03;  
  
// In this sample, INRECS is opened by using an OPEN FOR statement, and  
// INOUTRECS_IN is opened by calling the GET_ALL_ACTIVITY procedure on Oracle.  
  
namespace OracleRefCursorsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the client  
            SCOTTPackageACCOUNT_PKGClient accountPkgClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // Set credentials  
            accountPkgClient.ClientCredentials.UserName.UserName = "SCOTT";  
            accountPkgClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
  
                GET_ACTIVITYns.INOUTRECSRECORD[] strongCursor;  
                GENERICns.GenRecordRow[] weakCursor;  
  
                Console.WriteLine("Opening client");  
                // Open the client  
                accountPkgClient.Open();  
  
                Console.WriteLine("Invoking ACCOUNT_PKG.GET_ACTIVITY");  
                // Get  ACCOUNTACTIVITY records  
                // The IN REF CURSOR is set to all activity for account 100001  
                // The input part of the IN OUT ref cursor calls GET_ALL_ACTIVITY  
                // The weakly-typed OUT REF CURSOR parameter returns a list of activity for account 100001  
                // The strongly-typed IN OUT REF CURSOR parameter returns a list of all activity  
                string inRecsString = "BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;";  
                string inoutRecsString = "BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;";  
  
                accountPkgClient.GET_ACTIVITY(  
                                inRecsString,  
                                inoutRecsString,  
                                out strongCursor,  
                                out weakCursor);  
  
                // Display strong ref cursor (all activity)  
                Console.WriteLine("\nList of all activity returned (strong ref cursor)");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < strongCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2:C}\t{3}\t{4}",strongCursor[i].TID,  
                        strongCursor[i].ACCOUNT,   
                        strongCursor[i].AMOUNT,   
                        strongCursor[1].TRANSDATE,  
                        strongCursor[i].DESCRIPTION);  
                }  
  
                // Display weak ref cursor (account 100001)  
                Console.WriteLine("\nList of activity for account 100001 returned (weak ref cursor)");  
                Console.WriteLine("Tx Id\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < weakCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1:C}\t{2}\t{3}", weakCursor[i].GenRecordColumn[0].ColumnValue,  
                        weakCursor[i].GenRecordColumn[2].ColumnValue,  
                        weakCursor[i].GenRecordColumn[4].ColumnValue,  
                        weakCursor[i].GenRecordColumn[3].ColumnValue);  
                }  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
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
                // Close the client  
                accountPkgClient.Close();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)