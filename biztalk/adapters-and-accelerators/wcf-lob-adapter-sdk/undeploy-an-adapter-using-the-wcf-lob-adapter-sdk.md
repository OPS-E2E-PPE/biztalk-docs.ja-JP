---
title: WCF LOB アダプター SDK を使用してアダプターを展開解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84932fa0a140df157408ad77d9fc6bec8c0823fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974587"
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK を使用してアダプターを展開解除します。
コンピューターからアダプターを展開解除するには、ユーザーは、次の 2 つのタスクを実行する必要があります。  
  
1.  グローバル アセンブリ キャッシュ (GAC) から、アダプター アセンブリ (と任意の依存アセンブリ) をアンインストールします。  
  
2.  Machine.config ファイルで、アダプターのバインドとアダプターのバインド要素を削除します。  
  
## <a name="uninstall-an-assembly-from-the-gac"></a>アセンブリを GAC からアンインストールします。  
  
#### <a name="use-the-windows-interface"></a>Windows インターフェイスを使用してください。  
  
1.  次のように Windows エクスプ ローラーを開く: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**.  
  
2.  Systemdrive%\Windows\Assembly に置かれている、GAC に参照します。  
  
3.  アプリケーションに含まれている各アセンブリ ファイルを右クリックし、をクリックして**アンインストール**、 をクリックし、**はい**を確認します。  
  
#### <a name="use-the-command-line"></a>コマンドラインを使用してください。  
  
1. 開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。  
  
2. コマンド プロンプトで、次のコマンドを入力します。  
  
    **gacutil/u** \<*の完全修飾*<em>アセンブリ名</em>\>  
  
    このコマンドでは、アセンブリ名は、GAC からアンインストールするアセンブリの名前です。  
  
    アセンブリ hello.dll を GAC から削除する例を次に示します。  
  
    `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a>アダプターのバインドを Machine.config ファイルから削除します。  
 アダプターのバインドを削除する machine.config ファイルを編集して手動でまたはサービス構成エディターを使用できます。 このセクションでは、両方の手順を示します。 
  
#### <a name="manually-edit-the-machineconfig-file"></a>Machine.config ファイルを手動で編集します。  
  
1.  Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、次のようにクリックします**開始**、 をクリック**実行**、型**メモ帳\<Windows インストール パス\>\Microsoft.NET\Framework\\< バージョン\>。\CONFIG\machine.config**、 をクリックし、 **OK**します。  
  
    > [!NOTE]
    >  編集のミスから保護するための変更を加える前に、machine.config ファイルのバックアップを作成します。  
  
2.  Machine.config ファイルを更新します。 削除するアダプターの bindingExtensions 要素を探します。 存在するその他の情報に基づき、次のいずれかの操作を行います。  
  
    -   その他の bindingExtensions がある場合は、アダプター拡張機能のみを削除します。  
  
    -   その他の bindingExtensions がない場合 (アダプター拡張機能を含む) bindingExtensions セクションを削除できます。  
  
    -   他 bindingExtensions または拡張機能がない場合は、拡張機能セクションを削除できます。  
  
    -   最後に、system.serviceModel にアダプター拡張機能のみが含まれている場合は、全体の system.serviceModel セクションを削除できます。  
  
3.  BindingElementExtensions 要素に対して、手順 2. を繰り返します。  
  
4.  machine.config ファイルを閉じて保存します。  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a>サービス構成エディターを使用して、machine.config ファイルを変更しないでください。  
  
1.  サービス構成エディタを開きます。 参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。
  
2.  ツリー ビュー ペインで (というラベルの付いた**構成**)、ノード ツリーを展開します。 をクリックして、 **詳細設定**フォルダー、 をクリックして、**拡張**フォルダー、およびバインド拡張機能の要素を選択します。  
  
3.  バインド拡張機能のエディターの詳細ウィンドウで、削除、およびクリックするバインド拡張機能をクリックします。**削除**します。 次の図に MyAdapterExtension が強調表示され、削除されます。  
  
     ![拡張機能が追加されたサービス構成エディター。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")  
  
4.  サービス構成エディタを閉じます。  
  
## <a name="see-also"></a>参照  
 [WCF LOB アダプター SDK を使用して、アダプターを展開します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)