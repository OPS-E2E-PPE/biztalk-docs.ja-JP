---
title: "WCF LOB Adapter SDK と WSDL の生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1075bbe59e15e3eeabde6c1d5c954460d1cb570
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK と WSDL を生成します。
アダプター、または LOB システムの変更から返されるメタデータは多くの場合、操作のメタデータが生成されることを確認するアダプターから返される Web サービス記述言語 (WSDL) を表示すると便利開発時に正しくです。 WSDL を生成するいくつかの方法があります。 このトピックでは、svcutil.exe とメタデータ検索参照コントロールの使用に関する情報を提供します。  

  
## <a name="use-svcutilexe"></a>Svcutil.exe を使用してください。  
 Svcutil.exe は、URL と省略可能なスイッチを受け取り、WSDL を返す Windows SDK に付属してコマンド ライン ユーティリティです。 Svcutil.exe を使用してエコー アダプターの WSDL を取得する例を次に示します。  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 これにより、メタデータが Microsoft.Adapters.Samples.Echov2.wsdl として保存します。 場合は、アダプターは、多くの操作を使用して、目的の操作だけを返すことができます ' op OperationName =' URI の一部として。 これを使用して EchoStrings 情報のみを返す例を次に示します。  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>メタデータの検索の参照機能付きコントロールを使用します。  
 メタデータ検索参照コントロールに含まれるウィザードで使用されている Windows コントロール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 Visual Studio で、任意の Windows フォーム プロジェクトにこのコントロールを追加し、アダプターでは、目的の操作を選択して、WSDL を生成できます。  
  
1.  開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。  
  
2.  **ファイル**メニューの **新規**、クリックして**プロジェクト**です。  
  
3.  **新しいプロジェクト**ダイアログ ボックスで、 **Windows アプリケーション**から**テンプレート**です。 プロジェクト名を入力し、クリックして**OK**です。  
  
4.  開く、**ツールボックス**、展開**コモン コントロール**を右クリックし、**ツールボックス**、順にクリック**アイテムの選択**です。  
  
5.  **ツールボックス アイテムの選択**ダイアログ ボックスで、検索**MetadataUserControl**上、**の .NET Framework コンポーネント** タブで、この項目の横にあるチェック ボックスをオンにし、 をクリックして**Ok**です。  
  
6.  [ツールボックス] から、MetadataUserControl を Form1 にドラッグします。 コントロール全体を表示するフォームのサイズを変更する必要があります。 できます、プロジェクトを今すぐ実行し、コントロールが、機能していることを確認するアダプターと操作を選択することができます。  
  
7.  このコントロールを使用して WSDL を生成するを呼び出して、フォームにコードを追加する必要があります、 **GetWsdl**このコントロールのメソッドです。 次の例を呼び出す方法**GetWsdl**ファイルにデータを保存します。  
  
    ```csharp  
    private void button1_Click(object sender, EventArgs e)  
    {  
       ServiceDescription sd = mdUserControl.GetWsdl();  
       FileStream myFileStream = new FileStream(tbWsdlFileName.Text, FileMode.OpenOrCreate, FileAccess.Write);  
       StreamWriter myStreamWriter = new StreamWriter(myFileStream);  
       sd.Write(myStreamWriter);  
       myStreamWriter.Flush();  
       myStreamWriter.Close();  
       MessageBox.Show("WSDL file " + tbWsdlFileName.Text + " is created.");  
    }  
  
    ```  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)