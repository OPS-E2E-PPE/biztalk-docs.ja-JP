---
title: Siebel にポートのバインド ファイルを使用して物理的なポート バインドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring by using a port binding file
ms.assetid: 1758e89c-d56c-4e67-919b-c0bbb22878bf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10eb723c671a94fd95c7ed21a14c93fad3f907c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371945"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-siebel"></a>Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成します。
使用すると、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータ スキーマ ファイル以外の Siebel 成果物を生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ポートのバインド ファイルも生成されます。 物理送信ポートを作成する BizTalk アプリケーションには、このバインド ファイルをインポートできます。 参照してください[Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)します。 このバインド ファイルをインポートする場合、物理送信ポートを手動で作成することはありません。  
  
> [!IMPORTANT]
>  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値は null し、プロパティのバインドが使用できないこと、バインド ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、バインド ファイルに必要な場合。  
  
 ポートのバインド ファイルを常に使用するポートを作成するには、双方向送信ポートが作成されます。 一方向のポートを作成する場合は、手動で作成する」の手順に従って[Siebel にポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)します。 または、一方向のポートを作成するポートのバインド ファイルを変更するには、このトピックに記載されている回避策を利用できます。  
  
> [!IMPORTANT]
>  使用して、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] Wcf-siebel ポートを作成することができますを使用してポートのバインド ファイルを作成しません。 ただし、によって生成されたポートのバインド ファイルにいくつかの変更を加える可能性があります、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Wcf-siebel ポートの作成に使用します。 詳細については、ポートのバインド ファイルが生成を使用して Consume Adapter Service アドインを使用して WCF Siebel ポートの構成を参照してください。  
  
 によって生成されたバインド ファイルに関して理解しておく必要があります重要な点を次に、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   ファイルは、特定の名前付け規則で作成されます。 Siebel システムへのメッセージを送信するには、送信の操作のメタデータを生成した場合は、WcfSendPort_SiebelBinding_Custom.bindinginfo.xml は、ファイルの名前。  
  
-   ファイルには、バインド構成、バインディングの種類、エンドポイントの URI、およびメタデータの生成対象の操作に基づき、ポートのアクションに関する情報が含まれています。 ポートを作成するには、このバインド ファイルをインポートするときに物理ポートを構成するために必要なすべての関連情報がポートで自動的に設定します。  
  
    > [!IMPORTANT]
    >  既定では、送信ポートのアクションは、メタデータを生成する操作名にマップされます。 たとえば、アカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成する場合、ポートのアクションに設定されて`<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />`します。 ただし、BizTalk オーケストレーションで作成する論理送信ポートでの操作名が同じになりません。 (BizTalk オーケストレーション) の論理ポートと物理送信ポート (BizTalk Server 管理コンソール) での操作名が同じであることを確認する必要があります。 それ以外の場合は、送信ポートを使用して Siebel システムへのメッセージの送信中にエラーが表示されます。  
  
-   Siebel システムへの接続にポートの資格情報を提供するだけです。 バインド ファイルには、接続先となるユーザー名を保持は、セキュリティ上の理由から、バインド ファイルにが含まれていませんパスワードには。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>ポートのバインド ファイルを使用するための重要な考慮事項  
  
-   バインド ファイルをインポートすると、バインド ファイル内の BizTalk アプリケーション名が、バインド ファイルをインポートするアプリケーション名と一致しないことを通知ダイアログ メッセージを取得可能性があります。 安全に、このメッセージは無視し、続行できます。  
  
-   バインド ファイルは、ポートの名前を含むもと受信場所。 バインド ファイルをインポートする BizTalk アプリケーションでは、ポート、または、同じ BizTalk アプリケーションに既に既存のポートと同じ名前を持つ受信場所を作成する場合は、エラーが発生します。 ポートの一意の名前を指定するか、受信場所にバインド ファイルを手動で編集する必要があります。  
  
-   既定では、ポートのバインド ファイルには、双方向の送信ポートの定義が常に含まれます。 BizTalk アプリケーションでは、このファイルをインポートするときに、双方向送信ポートを作成します。 ただし、一方向の送信ポートを持つオーケストレーションがあります。 そのため、このようなオーケストレーションを構成して、バインド ファイルをインポートすることによって作成されたポートを使用するときに、ポートは、一覧では使用できません。 これは、オーケストレーションの一部として作成した論理ポートは一方向のポート、オーケストレーション内に作成する物理ポートは双方向のポートのために発生します。 このような場合は、次の変更をバインド ファイルを編集できます。  
  
    |こちらは|方法|  
    |--------------|-------------|  
    |構成するポートのバインド ファイルを編集するには、一方向送信ポート|次の例での値を変更する**IsTwoWay**プロパティを**false**します。 設定されていた、 **true**します。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -次の抜粋をコメント化します。<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-siebel-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>アダプターを使用して、使用して生成されたポートのバインド ファイルを使用して WCF Siebel ポートを構成する追加のサービス  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でインポートできるポートのバインド ファイルも作成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 同じポートのバインド ファイルを使用しても BizTalk Wcf-siebel ポートを作成することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 ただし、Wcf-siebel ポートを作成する前に、ポートのバインド ファイルを変更するのには、次のタスクを実行する必要があります。  
  
1. ポートのバインド ファイルをテキスト エディターで開きます。  
  
2. 検索し、の Wcf-siebel アダプターを追加する名前を持つ"Wcf-custom"を置換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 たとえば、"SiebelAdapter"として Wcf-siebel アダプターを追加した場合は、"SiebelAdapter"と"Wcf-custom"を置き換えます。  
  
3. "ConfigurationClsid"属性を検索し、既存の属性の値を"7971A78D-AE8F-42B4-834D-3A957FD945E9"に置き換えます。  
  
4. 保存して、バインド ファイルを閉じます。  
  
5. バインド ファイル インポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 参照してください[Siebel アダプターのアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)します。 
  
## <a name="see-also"></a>参照  
[の構成要素、Siebel を BizTalk アプリケーションを作成するには 

adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)