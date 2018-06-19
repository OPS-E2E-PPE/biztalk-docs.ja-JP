---
title: '手順 9: ビルド アダプターおよび展開エコー |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b9a4985629427e44b8ca85f324c89ab719cf249
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967240"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a>手順 9: ビルドをエコー アダプターの展開
![手順 9 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 **所要時間:** 10 分  
  
 このステップでは、エコー アダプターの展開に必要なタスクを実行します。 次のすべてが含まれます。  
  
-   厳密な名前のファイルを作成し、エコー アダプターのアセンブリに割り当てます  
  
-   エコー アダプターをビルドします。  
  
-   GAC にアセンブリを公開します。  
  
-   エコー アダプターを登録します[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]  
  
## <a name="prerequisites"></a>前提条件  
 この手順を正常に完了するには、厳密な名前のファイルと、GAC に精通しての操作をおく必要があります。 基本的な知識[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]構成は役立ちますが、必須ではありません。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てるには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**プロパティ**です。  
  
2.  EchoAdapter プロパティ ページ ダイアログ ボックスで、次のように選択します。**署名**左側のペインからです。  
  
3.  クリックして、**アセンブリに署名**タブです。  
  
4.  選択**\<新規作成しています.\>** 厳密な名前のファイルです。 ファイル名の入力を求め、入力**EchoAdapter.snk**保護するオプションでは、パスワード、キー ファイルの選択を解除し、クリックして**OK**です。  
  
5.  クリックして、**アプリケーション**タブです。  
  
6.  アセンブリ名に変更**Microsoft.Adapters.Samples.EchoV2**です。  
  
7.  をクリックして**ファイル**、Visual Studio のメニューをクリックし**すべて保存**です。  
  
### <a name="to-build-and-deploy-echo-adapter"></a>構築およびデプロイ エコー アダプター  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**ビルド**です。 ビルドが成功しなかった場合は、エラーを修正して、エコー アダプターを再構築してください。  
  
2.  Visual Studio コマンド プロンプトを開きます。  
  
3.  次のコマンドを入力します。  
  
     **gacutil.exe/if"\<**  *assembly\Microsoft.Adapters.Samples.EchoV2.dll へのパス*  **\>"**  
  
     これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a>Windows Communication Foundation にエコー アダプターを登録するには  
  
1.  Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、をクリックして**開始**をクリックして**実行**、型**メモ帳\<Windows のインストール パス\>\Microsoft.NET\Framework\\< バージョン\>\CONFIG\machine.config**、クリックして**OK**です。  
  
2.  Machine.config ファイルを更新します。 Machine.config に system.serviceModel セクションが含まれていない場合は、ルート タグの終わりの前に、構成ファイルの末尾に次のセクションを追加します。  
  
    > [!NOTE]
    >  バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。  
  
    ```  
    <system.serviceModel>  
      <client>  
        <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
          name="echov2" />  
      </client>  
      <extensions>  
        <bindingElementExtensions>  
          <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingElementExtensions>  
        <bindingExtensions>  
          <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
     - または -  
  
     Machine.config system.serviceModel セクションが含まれている場合は、のどの要素が見つからないと追加を決定します。  
  
    > [!NOTE]
    >  バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。  
  
    ```  
    <client>  
      <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
        name="echov2" />  
    </client>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingElementExtensions>  
      <bindingExtensions>  
        <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingExtensions>  
    </extensions>  
    ```  
  
3.  Machine.config ファイルを保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 エコー アダプター チュートリアルの最後の手順で、エコー アダプターに厳密な名前を追加、構築して、アダプターを展開し、するアダプターに関する情報が含まれる Machine.config を変更します。 この時点では、エコー アダプターはアプリケーションの処理に使用できるはずです。  
  
## <a name="next-steps"></a>次の手順  
 このチュートリアルが完了しました。 .NET プロジェクトでエコー アダプターの機能をテストする場合は、「[チュートリアル 2: .NET からエコー アダプターを使用する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 8: エコー アダプターの同期受信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)   
 [チュートリアル 2: .NET からエコー アダプターを使用する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)