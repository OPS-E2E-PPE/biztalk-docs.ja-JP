---
title: WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bda1c864e7a6eff442099d6caf1a2bba98e7f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215978"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のデータベース成果物の操作の標準セットを表示します。 これらの操作を使用すると、Oracle 関数またはプロシージャの呼び出しなどの操作または基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。 ただし、シナリオが考えられます、ビジネス ロジックによって操作を実行する必要があること、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]発生しません。 たとえばをする可能性があります。  
  
-   表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle シーケンスの NEXTVAL を取得します。  
  
-   データ定義言語の操作です。たとえば、テーブルを作成します。  
  
-   デザイン時に存在しませんでした、データベースの成果物の操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。  
  
-   操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; たとえば、クエリを実行して、含む JOIN 句です。  
  
 これらのシナリオでは、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作を表示します。 SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化された SQL ステートメントを実行できます。 SQLEXECUTE 操作には、セットごとに、同じ SQL ステートメントを実行できるようにするパラメーター セットで構成される入力パラメーター ブロックがサポートされています。 SQLEXECUTE 操作は、レコード セットの汎用的な SQL ステートメントの結果を返します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックは、Oracle シーケンスを使用しての例では、TID_SEQ という名前です。 このシーケンスを生成するスクリプトは、SDK サンプルの値が提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 WCF サービス モデルには、専用の WCF クライアントが生成されます**SQLEXECUTEClient**、SQLEXECUTE 操作します。 次のコードは、 **SQLEXECUTEClient**と SQLEXECUTE 操作を呼び出すに呼び出すメソッドのシグネチャ。  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 SQLEXECUTE 操作では、汎用のレコード セットを返します。 このレコード セットが含まれています値には (存在する場合)、SQLEXECUTE 操作が実行されるステートメントによって返されます。 SQLEXECUTE 操作 PARAMETERDATA オブジェクトの文字列で表される入力パラメーターのコレクションを含む各コレクションには、入力パラメーターのセットを渡すことができます。 次のコードは、PARAMETERDATA 一連の定義を示しています。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a>SQLEXECUTE 操作を呼び出す  
 WCF クライアントを使用して、SQLEXECUTE 操作を呼び出すには、次の手順を実行します。  
  
1.  生成、 **SQLEXECUTEClient**対象のテーブルまたはビューのクラスです。  
  
    > [!IMPORTANT]
    >  SQLEXECUTE 操作がルート ノードの下に表示される (**/**) で、**カテゴリを選択**ペインで、**アダプター サービス参照の追加** ダイアログ ボックス。  
  
2.  インスタンスを作成、 **SQLEXECUTEClient**クラス、および呼び出し、 **SQLEXECUTE** Oracle データベースで SQL ステートメントを実行するメソッド。  
  
 詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。  
  
 次の例では、 **SQLEXECUTEClient**を次の SQL ステートメントを実行することによって Oracle シーケンス、TID_SEQ の次の値を取得する:`SELECT tid_seq.nextval id from DUAL`です。 出力がコンソールに書き込まれます。  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)