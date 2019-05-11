---
title: WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作の実行 |Microsoft Docs
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
ms.openlocfilehash: cf001bcfe96a2fb6849ce72ba5800117f62e618c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376060"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベース アイテムに対する操作の標準セットを明らかになります。 これらの操作を使用して、Oracle 関数またはプロシージャの呼び出しなどで行うまたは基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。 ただし、ある可能性があります、ビジネス ロジックによって操作を実行する必要があるシナリオを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]記録されません。 たとえば、しをたい場合があります。  
  
- 表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle のシーケンスの NEXTVAL を取得します。  
  
- データ定義言語の操作を実行します。たとえば、テーブルを作成します。  
  
- デザイン時に存在しませんでしたが、データベース成果物に対して操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。  
  
- 操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; JOIN 句を含むクエリを実行するなど。  
  
  このようなシナリオでの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]SQLEXECUTE 操作を表示します。 SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化 SQL ステートメントを実行できます。 SQLEXECUTE 操作のセットごとに、同じ SQL ステートメントを実行するためのパラメーター セットで構成される、入力パラメーター ブロックをサポートします。 SQLEXECUTE 操作は、ジェネリック レコード セット内の SQL ステートメントの結果を返します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックで使用して Oracle シーケンスの例では、TID_SEQ という名前です。 このシーケンスを生成するスクリプトは SDK のサンプルで提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 WCF サービス モデルは、専用の WCF クライアントを生成します**SQLEXECUTEClient**、SQLEXECUTE 操作。 次のコードは、 **SQLEXECUTEClient** SQLEXECUTE 操作を呼び出すために呼び出すメソッドのシグネチャとします。  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 SQLEXECUTE 操作には、汎用のレコード セットが返されます。 このレコード セットが含まれています、値には (ある場合) その SQLEXECUTE 操作の実行ステートメントによって返されます。 文字列として表される入力パラメーターのコレクションを含む各 PARAMETERDATA オブジェクトのコレクションで SQLEXECUTE 操作には、入力パラメーターのセットを渡すことができます。 次のコードでは、PARAMETERDATA セットの定義を示します。  
  
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
 SQLEXECUTE 操作を呼び出すには、WCF クライアントを使用してするには、次の手順を実行します。  
  
1. 生成、 **SQLEXECUTEClient**対象のテーブルまたはビューのクラス。  
  
   > [!IMPORTANT]
   >  SQLEXECUTE 操作は、ルート ノードの下に表示される (**/**) で、**カテゴリを選択**ペインで、**アダプター サービス参照の追加** ダイアログ ボックス。  
  
2. インスタンスを作成、 **SQLEXECUTEClient**クラス、および呼び出す、 **SQLEXECUTE** Oracle データベースで SQL ステートメントを実行するメソッド。  
  
   WCF クライアント クラスを作成し、操作を呼び出す方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)します。  
  
   次の例では、 **SQLEXECUTEClient**次の SQL ステートメントを実行することによって、TID_SEQ、Oracle シーケンスの次の値を取得する:`SELECT tid_seq.nextval id from DUAL`します。 出力は、コンソールに書き込まれます。  
  
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