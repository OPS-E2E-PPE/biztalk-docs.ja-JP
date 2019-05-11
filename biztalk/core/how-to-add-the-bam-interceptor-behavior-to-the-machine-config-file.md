---
title: BAM インターセプタ動作を Machine.config ファイルに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ef2ac191a50929be06fb5093d93382b63d2959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387300"
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a>BAM インターセプタ動作を Machine.config ファイルに追加する方法
Bam データをインターセプトするには、Microsoft .NET machine.config ファイルに、BAM インターセプタ動作を追加する必要があります。 これは、2 つの方法で行います。  
  
-   動作を追加する、machine.config ファイルを手動で編集します。  
  
-   動作を追加するのにには、サービス構成エディターを使用します。  
  
### <a name="to-manually-edit-the-machineconfig-file"></a>Machine.config ファイルを手動で編集するには  
  
1.  Microsoft .NET の構成フォルダーにある machine.config ファイルを編集します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、メモ帳の c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config を入力し、クリック**OK**します。  
  
2.  次の動作拡張機能では、machine.config ファイルを更新します。  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  Machine.config ファイルを保存して閉じます。  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a>サービス構成エディターを使用して machine.config ファイルを編集するには  
  
1.  サービス構成エディターを開きます。 サービス構成エディターの使用方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557)します。  
  
2.  ツリー ビュー ペインで (というラベルの付いた**構成**)、ノード ツリーを展開します。 をクリックして、 **詳細設定**フォルダー、 をクリックして、**拡張**フォルダー、および選択し、**動作要素拡張**要素。  
  
3.  新しい動作要素拡張を作成します。 をクリックして、**新規**ボタン Extension 構成要素エディタ ダイアログ ボックスを開きます。 **構成名**動作、BAMEndPointBehaviorExtension などの一意の名前を入力します。  
  
     ![Extension 構成要素エディタ](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")  
  
4.  をクリックして、**型**フィールドし、省略記号ボタンをクリックして (**.**)、動作拡張型ブラウザ ダイアログ ボックスを開くボタンをクリックします。  
  
5.  GAC の Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。  
  
6.  Microsoft.BizTalk.Bam.Interceptors アセンブリを選択します。  
  
7.  をクリックして、**オープン**アセンブリを選択するボタンをクリックし、ダイアログ ボックスを閉じます。  
  
     ![動作拡張型ブラウザー](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")  
  
8.  動作拡張型ブラウザ ダイアログ ボックスの [型名] ウィンドウで、Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 型 (として、次の画面で強調表示されている) をダブルクリックします。  
  
     ![動作拡張型ブラウザー](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")  
  
     拡張機能の構成要素エディタが開きます。  
  
9. クリックして**OK** Extension 構成要素エディタ ダイアログ ボックスを閉じます。  
  
10. サービス構成エディターの詳細ウィンドウで、BAMEndPointBehaviorExtension が表示されることを確認します。  
  
11. サービス構成エディターを閉じます。  
  
## <a name="next-steps"></a>次の手順  
 [BAM WCF インターセプションを構成する方法](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a>参照  
 [BAM データを受信するための WCF アダプターの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)