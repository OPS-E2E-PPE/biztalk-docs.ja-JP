---
title: WCF LOB アダプター SDK を使用して、アダプターの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c29400aae9a9bcd0cf36d49f9b619dc7642fa5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978475"
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK を使用して、アダプターを展開します。
アダプターを展開するには、アダプター アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールして、machine.config ファイルでアダプターを登録します。  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a>アダプターのアセンブリを GAC にインストールします。  
 Visual Studio を使用してアダプターを使用する前に、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]コマンドまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]機能、GAC にアセンブリをインストールする必要があります。 厳密な名前であるアセンブリだけを GAC にインストールできます。  
  
> [!NOTE]
>  この手順を完了するには、GAC に対する書き込み権限を持つアカウントでログオンする必要があります。 ローカル コンピューターの管理者アカウントには、これらのアクセス許可が与えられています。  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成します。  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、厳密な名前が必要なアダプター プロジェクト ファイルを読み込みます。  
  
2. 開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。  
  
3. コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
    **sn/k***file_name* **.snk**   
  
    例: **sn/k EchoAdapter.snk**  
  
    確認メッセージ、**キーのペアに書き込まれる** \< *file_name*\>**.snk** `,`コマンド ラインで表示されます。  
  
4. Visual Studio ソリューション エクスプ ローラーでプロジェクトを右クリックし、クリックして**プロパティ**します。  
  
5. 左側のウィンドウで展開**共通プロパティ**、 をクリックし、**アセンブリ**します。  
  
6. 右側のウィンドウのスクロール、**厳密な名前**ボックス。  
  
7. **厳密な名前**ボックスで、フィールドの横に **アセンブリ キー ファイル**、参照ボタンをクリックします (**.**)、キー ファイルを参照します。  
  
8. キー ファイルをクリックして**オープン**、順にクリックします**OK**します。  
  
9. Visual Studio のメニュー**ビルド**を選び、**ソリューションのビルド**。  
  
> [!NOTE]
>  アダプターのアセンブリは、他のアセンブリに依存する場合は、これらの参照先アセンブリが; 厳密な名前で署名されたことを確認します。それ以外の場合、エラーが発生します。  
  
 ソースがある場合は、前述のように厳密な名前で再コンパイルすることができます。 参照アセンブリがサード パーティに属する厳密な名前を指定があることを確認できない場合は、逆アセンブルし、厳密な名前でアセンブリを再構築し、できます。  
  
 元のアセンブリは上書きされます、元のバージョンを保持したい場合は、確認するため、次の手順に進む前のバックアップ コピーを作成します。  
  
 アセンブリを逆アセンブルするのにには、Microsoft Intermediate Language (MSIL) の逆アセンブラーを使用します。  
  
- ILDASM thirdparty.dll/out:thirdparty.il  
  
  MSIL アセンブラーを使用して、厳密な名前でアセンブリを再アセンブルします。  
  
- ILASM thirdparty.il/dll/key=strongkeyfile.snk  
  
#### <a name="install-an-assembly-in-the-gac"></a>アセンブリを GAC にインストールします。  
  
1. アダプターが署名されていることを確認します。  
  
2. 開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。  
  
3. 次のコマンドを入力します。  
  
    **gacutil.exe/if"\<**  *アセンブリ .dll ファイルへのパス*  **\>"**  
  
4. これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
## <a name="register-the-adapter-in-machineconfig"></a>Machine.config にアダプターを登録します。  
 使用して、アダプターの開発、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF バインドとして表示されます。  詳細については、Microsoft.ServiceModel.Channels.Common.AdapterBinding を参照してください。  Wcf アダプター バインドが登録されているを使用して\<bindingExtensions\>セクション内\<システム。ServiceModel\> wcf アダプターのトランスポート バインド要素が登録されているとを使用して\<bindingElementExtensions\>セクション内\<システム。ServiceModel\>します。  
  
 テキスト エディターを使用して、machine.config ファイルを手動で編集することができます。  
  
#### <a name="manually-edit-the-machineconfig-file"></a>Machine.config ファイルを手動で編集します。  
  
1. Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、次のようにクリックします**開始**、 をクリック**実行**、「notepad \<Windows インストール パス\>\Microsoft.NET\Framework\\< バージョン\>\CONFIG\。クリックして、machine.config **OK**します。  
  
2. Machine.config ファイルを更新します。 ファイルに system.serviceModel セクションが含まれていない場合は、終了タグをルートする前に、構成ファイルの末尾に次のセクションを追加します。  
  
   > [!NOTE]
   >  "MyAdapterBinding"、バージョン、カルチャ、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
           <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
       </bindingExtensions>      <bindingElementExtensions>  
           <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
         </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - または -  
  
     Machine.config ファイルに system.serviceModel セクションが含まれている場合は、要素が不足しているとアダプターの情報に置き換えて"MyAdapter"その他の情報を追加を決定します。  
  
   ```  
   <extensions>  
     <bindingExtensions>  
           <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
     </bindingExtensions>  
         <bindingElementExtensions>  
           <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
         </bindingElementExtensions>  
   </extensions>  
   ```  
  
3. machine.config ファイルを閉じて保存します。  
  
   使用することも、[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx) machine.config ファイルを変更します。
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a>サービス構成エディターを使用して、machine.config ファイルを編集します。  
  
1.  開く、**サービス構成エディター**します。 参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。
  
2.  ツリー ビュー ペインで (というラベルの付いた**構成**)、ノード ツリーを展開します。 をクリックして、 **詳細設定**フォルダー、 をクリックして、**拡張**フォルダー、およびバインド拡張機能の要素を選択します。  
  
     ![サービス構成エディター。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")  
  
3.  新しいバインディング拡張機能を作成します。 をクリックして、**新規**、拡張機能を開くにはボタン**構成要素エディタ** ダイアログ ボックス。 **構成名**、たとえば、拡張機能の一意の名前を入力*MyAdapterExtension*します。  
  
     ![Extension 構成要素エディタ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")  
  
4.  をクリックして、**型**フィールドし、省略記号ボタンをクリックして (**.**) を開く、**バインド拡張型ブラウザ** ダイアログ ボックス。  
  
5.  GAC に Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。  
  
6.  アダプターのアセンブリをクリックします。  
  
     ![拡張型ブラウザーの構築。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")  
  
7.  をクリックして、**オープン**ボタンをクリックして、アセンブリを選択します。  
  
8.  **バインディング拡張型ブラウザ** ダイアログ ボックスで、バインディング コレクションの要素を実装する型名をクリックします。  
  
     ![拡張型ブラウザーの構築。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")  
  
9. をクリックして、**オープン**種類を選択するボタンをクリックします。  
  
10. をクリックして**OK**を閉じる、 **Extension 構成要素エディタ** ダイアログ ボックス。  
  
11. 詳細ウィンドウで、**バインディング拡張エディター**、バインド拡張機能が表示されることを確認します。 MyAdapterExtension は次の図で強調表示されます。  
  
     ![拡張機能が追加されたサービス構成エディター。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
12. 閉じる、**サービス構成エディター**します。  
  
## <a name="see-also"></a>参照  
 [WCF LOB アダプター SDK を使用して、アダプターを展開します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)