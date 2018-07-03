---
title: WCF LOB Adapter SDK と WSDL の生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaf5ed992864c11d360baa30f35983f0082213b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971075"
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK と WSDL を生成します。
アダプター、または LOB システムの変更から返されるメタデータは多くの場合、操作のメタデータが生成されることを確認するアダプターから返される Web サービス記述言語 (WSDL) を確認するために、開発中に正しくします。 WSDL を生成するいくつかの方法はあります。 このトピックでは、svcutil.exe とメタデータの検索参照コントロールの使用に関する情報を提供します。  

  
## <a name="use-svcutilexe"></a>Svcutil.exe を使用してください。  
 Svcutil.exe は、URL と省略可能なスイッチを受け入れ、WSDL を返します Windows SDK に付属のコマンド ライン ユーティリティです。 Svcutil.exe を使用してエコー アダプターの WSDL を取得する例を次に示します。  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 これにより、メタデータが Microsoft.Adapters.Samples.Echov2.wsdl として保存します。 アダプターに多くの操作がある場合を使用して、目的の操作のみを返すことができます ' op OperationName =' の URI の一部として。 EchoStrings 情報のみを返すこれを使用する例を次に示します。  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>メタデータの検索の閲覧コントロールを使用して、  
 メタデータの検索参照コントロールに含まれているウィザードで使用されている Windows コントロール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 Visual Studio で、任意の Windows フォーム プロジェクトにこのコントロールを追加し、アダプターでは、目的の操作を選択して WSDL を生成できます。  
  
1. 開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。  
  
2. **ファイル**メニューの [**新規**、] をクリックし、**プロジェクト**します。  
  
3. **新しいプロジェクト**ダイアログ ボックスで、 **Windows アプリケーション**から**テンプレート**します。 プロジェクト名を入力し、クリックして**OK**します。  
  
4. 開く、**ツールボックス**、展開**コモン コントロール**を右クリックし、**ツールボックス**、順にクリックします**アイテムの選択**します。  
  
5. **ツールボックス アイテムの選択**ダイアログ ボックスで、検索**MetadataUserControl**上、**の .NET Framework コンポーネント**タブに、この項目の横にあるチェック ボックスをオンにしてをクリックして **[Ok]** します。  
  
6. ツールボックスから、MetadataUserControl を Form1 にドラッグします。 コントロール全体を表示するフォームのサイズを変更する必要があります。 はずプロジェクトを今すぐ実行して、コントロールが機能することを確認するアダプターと操作を選択することができます。  
  
7. このコントロールを使用して WSDL を生成するには、呼び出すように、フォームにコードを追加する必要があります、 **GetWsdl**このコントロールのメソッド。 次の例を呼び出す方法を示します**GetWsdl**ファイルにデータを保存します。  
  
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