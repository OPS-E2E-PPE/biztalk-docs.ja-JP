---
title: '手順 9: 構築し、エコー アダプターの展開 |Microsoft Docs'
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
ms.openlocfilehash: 58e0bae620c43504091c29ed2b03a33e0c7710c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980507"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a>手順 9: 構築し、エコー アダプターの展開
![手順 9 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 **所要時間:** 10 分  
  
 この手順では、エコー アダプターの展開に必要なタスクを実行します。 これは、次のすべてが含まれます。  
  
- 厳密な名前のファイルを作成し、エコー アダプターのアセンブリに割り当てる  
  
- エコー アダプターをビルドします。  
  
- GAC にアセンブリを公開します。  
  
- エコー アダプターを登録します [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]  
  
## <a name="prerequisites"></a>前提条件  
 この手順を正常に完了するには、厳密な名前のファイルと、GAC をよく理解します。 基本的な理解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]構成は役立ちますが、必須ではありません。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てるには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**プロパティ**します。  
  
2.  EchoAdapter プロパティ ページ] ダイアログ ボックスで、[**署名**左側のウィンドウ。  
  
3.  をクリックして、**アセンブリに署名**タブ。  
  
4.  選択**\<新しい.\>** 厳密な名前のファイル。 ファイル名を求められたら、入力**EchoAdapter.snk**保護ではパスワードのオプションでは、キー ファイルの選択を解除し、クリックして**OK**します。  
  
5.  をクリックして、**アプリケーション**タブ。  
  
6.  アセンブリ名を変更して**Microsoft.Adapters.Samples.EchoV2**します。  
  
7.  クリックして**ファイル**、Visual Studio のメニューをクリックし**すべて保存**します。  
  
### <a name="to-build-and-deploy-echo-adapter"></a>ビルドしてエコー アダプターをデプロイするには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**ビルド**します。 ビルドが成功しなかった場合は、エラーを修正してエコー アダプターをリビルドしてください。  
  
2.  Visual Studio コマンド プロンプトを開きます。  
  
3.  次のコマンドを入力します。  
  
     **gacutil.exe/if"\<**  *assembly\Microsoft.Adapters.Samples.EchoV2.dll へのパス*  **\>"**  
  
     これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a>Windows Communication Foundation でエコー アダプターを登録するには  
  
1. Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、次のようにクリックします**開始**、 をクリック**実行**、型**メモ帳\<Windows インストール パス\>\Microsoft.NET\Framework\\< バージョン\>。\CONFIG\machine.config**、 をクリックし、 **OK**します。  
  
2. Machine.config ファイルを更新します。 Machine.config に system.serviceModel セクションが含まれていない場合は、終了タグをルートする前に、構成ファイルの末尾に次のセクションを追加します。  
  
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
  
     Machine.config に system.serviceModel セクションが含まれている場合は、要素が見つからないと追加を決定します。  
  
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
  
3. Machine.config ファイルを保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 エコー アダプターのチュートリアルの最後の手順でしてエコー アダプターに厳密な名前を追加、構築された、アダプターを展開し、アダプター情報を含めるように Machine.config の変更します。 この時点では、エコー アダプターは、アプリケーションを使用できるようにします。  
  
## <a name="next-steps"></a>次の手順  
 このチュートリアルが完了しました。 .NET プロジェクトでエコー アダプターの機能をテストする場合は、「[チュートリアル 2: .NET からエコー アダプターを使用](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 8: エコー アダプターの同期受信ハンドラーを実装する.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)   
 [チュートリアル 2: .NET からエコー アダプターを使用する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)