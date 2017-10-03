---
title: "BAM インターセプタ動作を Machine.config ファイルに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8845333389c95ea52d440437935d4c4867dc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a>BAM インターセプタ動作を Machine.config ファイルに追加する方法
BAM でデータを受信するには、BAM インターセプタ動作を Microsoft .NET machine.config ファイルに追加する必要があります。 これは次の 2 つの方法で実行できます。  
  
-   machine.config ファイルを手動で編集して動作を追加する。  
  
-   サービス構成エディタを使用して動作を追加する。  
  
### <a name="to-manually-edit-the-machineconfig-file"></a>machine.config ファイルを手動で編集するには  
  
1.  Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。 これを行うには、をクリックして**開始**、 をクリックして**実行**notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config」を入力して、をクリックして**OK**です。  
  
2.  次の動作拡張機能を追加して machine.config ファイルを更新します。  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  machine.config ファイルを閉じて保存します。  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a>サービス構成エディタを使用して machine.config ファイルを編集するには  
  
1.  サービス構成エディターを開きます。 サービス構成エディターの使用方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557)です。  
  
2.  ツリー ビュー ウィンドウ (ラベルの付いた**構成**)、ノード ツリーを展開します。 をクリックして、 **[詳細設定]**フォルダー、をクリックして、**拡張機能**フォルダーをクリックし、**動作要素拡張**要素。  
  
3.  新しい動作要素の拡張機能を作成します。 クリックして、**新規**Extension 構成要素エディタ ダイアログ ボックスを開きます。 **構成名**動作、BAMEndPointBehaviorExtension などの一意の名前を入力します。  
  
     ![Extension 構成要素エディタ](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")  
  
4.  クリックして、**型**フィールドに、省略記号ボタンをクリックして (**.**) 動作拡張型ブラウザ ダイアログ ボックスを開くボタンをクリックします。  
  
5.  グローバル アセンブリ キャッシュ (GAC) アイコンをクリックして、GAC の DLL を一覧表示します。  
  
6.  Microsoft.BizTalk.Bam.Interceptors アセンブリを選択します。  
  
7.  クリックして、**開く**アセンブリを選択するボタンをクリックし、ダイアログ ボックスを閉じます。  
  
     ![動作拡張型ブラウザー](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")  
  
8.  動作拡張型ブラウザ ダイアログ ボックスの型名ペインで、Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 型をダブルクリックします (次の画面の強調表示されている部分を参照)。  
  
     ![動作拡張型ブラウザー](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")  
  
     これにより、Extension 構成要素エディタが開きます。  
  
9. をクリックして**OK** Extension 構成要素エディタ ダイアログ ボックスを閉じます。  
  
10. サービス構成エディタの詳細ペインで、BAMEndPointBehaviorExtension が表示されていることを確認します。  
  
11. サービス構成エディタを閉じます。  
  
## <a name="next-steps"></a>次の手順  
 [BAM WCF インターセプションを構成する方法](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a>参照  
 [BAM データを受信する WCF アダプタの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)