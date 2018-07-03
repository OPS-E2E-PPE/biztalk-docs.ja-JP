---
title: Machine.config からバインド拡張機能を取得中にエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65ab48cf-575b-4db6-984a-880f7e286959
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c65c0341941634bb11bd058bfcbe9c365c612d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990731"
---
# <a name="error-getting-binding-extensions-from-machineconfig"></a>machine.config からバインド拡張機能を取得中にエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                machine.config からバインド拡張機能を取得中にエラーが発生しました                |
  
## <a name="explanation"></a>説明  
 このエラーは、受信場所または送信ポートのバインディング構成にはユーザー定義のバインディング拡張機能がありますが、machine.config ファイルに定義されていないときに発生します。 この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 受信場所または送信ポートに使用されているバインディング拡張機能を machine.config ファイルに定義します。 また、カスタムの動作またはバインディング要素を WCF-Custom アダプターで使用するには、次の手順を実行します。  
  
1.  アセンブリを GAC にします。  
  
2.  Machine.config ファイルを変更 (で見つかった **%FrameworkDir%\v4.0.30319\CONFIG**)。  
  
    1.  動作のサービス構成エディター内で DLL を読み込む (**svcConfigEditor.exe**)。  
  
    2.  構成を保存、 **app.config**ファイル  
  
    3.  コピーして貼り付け、 **system.servicemodel** machine.config の同様のセクションの extensions セクション。場合**system.servicemodel**セクションがあります、machine.config に存在しない 1 つを作成します。 次に、machine.config ファイルの構成セクションの例を示します。  
  
        ```  
          <system.serviceModel>  
            <extensions>  
              <behaviorExtensions>  
                <add name="BizTalkWcfContractNamespaceTestServiceBehaviorExtension" type="ASB.BizTalk.Samples.BizTalkWcfContractNamespaceTestServiceBehaviorExtension, CustomBizTalkWcfBehaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=7631521c07cf34b4" />  
              </behaviorExtensions>  
            </extensions>  
          </system.serviceModel>  
        ```  
  
> [!NOTE]
>  上記のコードは、WCF 拡張機能 タブにも追加できます。場合は、拡張機能は、受信側である必要がありますを参照してください、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能**タブ (Wcf-custom または Wcf-customisolated アダプターの受信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 表示拡張機能は、送信側である必要があります、 **\<ホスト名\>プロパティ ダイアログ ボックスで、WCF 拡張機能** タブ (Wcf-custom アダプターの送信ハンドラー)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  
  
 3. 管理コンソールを閉じ、開き直します。 WCF-Custom アダプターのカスタム動作を確認できるようになります。また、管理コンソールを開くと、ポートは有効なままです。