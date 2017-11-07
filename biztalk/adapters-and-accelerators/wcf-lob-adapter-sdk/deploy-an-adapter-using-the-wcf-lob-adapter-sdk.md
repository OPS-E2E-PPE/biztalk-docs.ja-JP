---
title: "WCF LOB アダプター SDK を使用して、アダプターの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c83998bbe16899055c839a73795d456a132381
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK を使用して、アダプターを展開します。
アダプターを展開するにはアダプター アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、machine.config ファイルにアダプターを登録します。  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a>アダプター アセンブリを GAC にインストールします。  
 Visual Studio を使用してアダプターを使用する前に、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]コマンドまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]機能、アセンブリを GAC にインストールする必要があります。 厳密な名前であるアセンブリのみを GAC にインストールできます。  
  
> [!NOTE]
>  この手順を完了するには、GAC に対する書き込み権限を持つアカウントでログオンする必要があります。 ローカル コンピューターの管理者アカウントには、これらのアクセス許可が与えられています。  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリ キー ファイルを構成します。  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、厳密な名前が必要なアダプター プロジェクト ファイルを読み込めません。  
  
2.  開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。  
  
3.  コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。  
  
     **sn/k***file_name* **.snk**   
  
     例: **sn/k EchoAdapter.snk**  
  
     確認メッセージを**キーのペアに書き込まれる** \< *file_name*>**.snk** `,`コマンド ラインで表示されます。  
  
4.  Visual Studio ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**プロパティ**です。  
  
5.  左側のウィンドウで展開**共通プロパティ**、クリックして**アセンブリ**です。  
  
6.  右側のペインでまでスクロールし、**厳密な名前**ボックス。  
  
7.  **厳密な名前**ボックス フィールドをクリックして、横に**アセンブリ キー ファイル**、参照ボタンをクリックして (**.**)、キー ファイルを参照します。  
  
8.  キー ファイルをクリックし、をクリックして**開く**、順にクリック**OK**です。  
  
9. Visual Studio のメニューをクリックして**ビルド**を選択し**ソリューションのビルド**です。  
  
> [!NOTE]
>  アダプターのアセンブリは、他のアセンブリに依存している場合は、これらの参照先アセンブリが厳密な名前で署名されたことを確認します。それ以外の場合、エラーが表示されます。  
  
 ソースがある場合は、上記のように厳密な名前で再コンパイルすることができます。 参照アセンブリ、サードパーティに属している、厳密な名前を指定、ことを確認できない場合は、逆アセンブルし、厳密な名前でアセンブリを再構成できます。  
  
 元のアセンブリは上書きされるため、元のバージョンを保持する場合を確認する、次の手順に進む前のバックアップ コピーを作成します。  
  
 Microsoft Intermediate Language (MSIL) の逆アセンブラーを使用して、アセンブリを逆アセンブルします。  
  
-   ILDASM thirdparty.dll/out:thirdparty.il  
  
 MSIL アセンブラーを使用して、厳密な名前でアセンブリを再アセンブルします。  
  
-   ILASM thirdparty.il/dll/key=strongkeyfile.snk  
  
#### <a name="install-an-assembly-in-the-gac"></a>アセンブリを GAC にインストールします。  
  
1.  アダプターが署名されていることを確認します。  
  
2.  開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。  
  
3.  次のコマンドを入力します。  
  
     **gacutil.exe/if"\<**  *アセンブリ .dll ファイルのパスを* **>"**  
  
4.  これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
## <a name="register-the-adapter-in-machineconfig"></a>Machine.config でアダプターを登録します。  
 使用して、アダプターの開発、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF バインドとして表示されます。  詳細については、Microsoft.ServiceModel.Channels.Common.AdapterBinding を参照してください。  WCF アダプター バインドに登録を使用して\<bindingExtensions > セクション内\<システムです。ServiceModel > WCF アダプター トランスポートのバインド要素が登録されるとを使用して\<bindingElementExtensions > セクション内\<システムです。ServiceModel >。  
  
 テキスト エディターを使用して、machine.config ファイルを手動で編集することができます。  
  
#### <a name="manually-edit-the-machineconfig-file"></a>Machine.config ファイルを手動で編集します。  
  
1.  Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、をクリックして**開始**をクリックして**実行**、「notepad \<Windows のインストール パス > \Microsoft.NET\Framework\\< バージョン\>\CONFIG\machine.config、クリックして**OK**です。  
  
2.  Machine.config ファイルを更新します。 ファイルに system.serviceModel セクションが含まれていない場合は、ルート タグの終わりの前に、構成ファイルの末尾に次のセクションを追加します。  
  
    > [!NOTE]
    >  "MyAdapterBinding"、バージョン、カルチャ、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。  
  
    ```  
    \<system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
        </bindingExtensions>      <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
      </extensions>  
    \</system.serviceModel>  
    ```  
  
     - または -  
  
     Machine.config ファイルの system.serviceModel セクションが含まれている場合は、のどの要素が不足しているは、"MyAdapter"とその他の情報をアダプターの情報に置き換えるを加算してを決定します。  
  
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
  
3.  machine.config ファイルを閉じて保存します。  
  
 使用することも、[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx) machine.config ファイルを変更します。
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a>サービス構成エディターを使用して、machine.config ファイルを編集します。  
  
1.  開く、**サービス構成エディター**です。 参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。
  
2.  ツリー ビュー ウィンドウ (ラベルの付いた**構成**)、ノード ツリーを展開します。 をクリックして、 **[詳細設定]**フォルダーで、をクリックして、**拡張機能**フォルダー、およびバインド拡張要素を選択します。  
  
     ![サービス構成エディター。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")  
  
3.  新しいバインディング拡張を作成します。 クリックして、**新規**を開くには、拡張ボタン**構成要素エディタ** ダイアログ ボックス。 **構成名**、たとえば、拡張機能の一意の名前を入力*MyAdapterExtension*です。  
  
     ![Extension 構成要素エディタ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")  
  
4.  クリックして、**型**フィールドに、省略記号ボタンをクリックして (**.**) を開くには、**バインド拡張型ブラウザー**  ダイアログ ボックス。  
  
5.  GAC の Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。  
  
6.  アダプターのアセンブリをクリックします。  
  
     ![拡張型ブラウザーの構築します。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")  
  
7.  クリックして、**開く**ボタンをクリックして、アセンブリを選択します。  
  
8.  **バインド拡張型ブラウザー**  ダイアログ ボックスで、バインディング コレクションの要素を実装した型名をクリックします。  
  
     ![拡張型ブラウザーの構築します。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")  
  
9. クリックして、**開く**ボタンの種類を選択します。  
  
10. をクリックして**OK**を閉じる、 **Extension 構成要素エディタ** ダイアログ ボックス。  
  
11. 詳細ウィンドウで、**バインディング拡張エディター**、バインド拡張機能が表示されることを確認してください。 次の図に MyAdapterExtension は強調表示されます。  
  
     ![追加された拡張機能とサービス構成エディター。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
12. 閉じる、**サービス構成エディター**です。  
  
## <a name="see-also"></a>参照  
 [WCF LOB アダプター SDK を使用して、アダプターを展開します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)