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
ms.openlocfilehash: 0ba98838d56287453b8d0b162dc531dbc3c1cbc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388823"
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
 受信場所のときに、このエラーが発生しますが、送信ポートのバインドの構成では、ユーザー定義のバインディング拡張機能または machine.config ファイルで定義されていません。 Wcf-custom および Wcf-customisolated アダプターで主に、このような状況が発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 Machine.config ファイルでの送信ポートまたは受信場所で使用されるバインド拡張機能を定義します。 また、カスタムの動作または WCF カスタム アダプターを使用するバインド要素を取得するには、この手順を完了します。  
  
1.  GAC アセンブリ  
  
2.  Machine.config ファイルを変更 (で見つかった **%FrameworkDir%\v4.0.30319\CONFIG**)。  
  
    1.  動作のサービス構成エディター内で DLL を読み込む (**svcConfigEditor.exe**)。  
  
    2.  構成を保存、 **app.config**ファイル  
  
    3.  コピーして貼り付け、 **system.servicemodel** machine.config の同様のセクションの extensions セクション。場合**system.servicemodel**セクションがあります、machine.config に存在しない 1 つを作成します。 Machine.config ファイルの構成セクションの例を次に示します。  
  
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
  
 3. 管理コンソールを閉じてから。 WCF カスタム アダプターのカスタム動作を確認できるし、有効にすると、ポートを有効になっている維持する必要があります。