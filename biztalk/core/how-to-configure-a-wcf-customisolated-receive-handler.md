---
title: Wcf-customisolated 受信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e90add2-1a5e-4509-a98c-b3c297b4213f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00e52daaaefc3f85537dc3c51f8700da30b74876
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248538"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a>WCF-CustomIsolated 受信ハンドラーを構成する方法
WCF-CustomIsolated アダプターで machine.config 以外の場所からカスタム動作拡張機能を検索する場合は、受信ハンドラーのプロパティを構成する必要があります。  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>Should WCF-CustomIsolated アダプターが machine.config 以外の場所からカスタム動作拡張機能を検索する理由  
 によって使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。動作拡張機能を読み込む前に、Wcf-customisolated アダプターは、machine.config で動作拡張機能を検索します。ただし、machine.config は、理想的には、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用されます。 一方、WCF カスタム動作拡張機能はコンピューターで実行されているすべてのアプリケーションではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でのみ要求されることがあります。 したがって、machine.config にカスタム動作拡張機能を保存すれば目的にかないますが、ここは最適な場所ではありません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、WCF-CustomIsolated アダプターがカスタム動作拡張機能を参照するための追加の場所をアダプター ハンドラーのプロパティで指定します。 machine.config で既に利用可能な動作拡張機能を置き換えるものではないことに注意してください。  
  
### <a name="additional-considerations"></a>その他の注意点  
 WCF-CustomIsolated 受信ハンドラーのプロパティを構成する際は、次の点を考慮してください。  
  
-   カスタム動作拡張機能は machine.config かアダプター ハンドラーのプロパティのどちらか一方で利用可能にする必要があります。 カスタム動作拡張機能を両方の場所に重複して設定しないでください。  
  
-   カスタム動作拡張機能が既に machine.config で利用できる場合、同じカスタム動作拡張機能をアダプター ハンドラーのプロパティに設定しようとすると、すぐにエラーが発生します。  
  
-   カスタム動作拡張機能が既にアダプター ハンドラーのプロパティに設定されている場合、machine.config を同じカスタム動作拡張機能で更新すると、実行時エラーが発生し、イベント ログにも記録されます。 受信場所も無効になります。  
  
-   アダプター ハンドラーのプロパティを設定する前に、カスタム動作拡張機能で参照されるアセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。  
  
## <a name="configuring-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティの構成  
 WCF-CustomIsolated 受信ハンドラーを構成するには、次の手順を使用します。  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティを構成するには  
  
1.  BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**Wcf-customisolated**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられているホストを選択し、をクリックして**プロパティ**です。  
  
4.  **Wcf-customisolated トランスポートのプロパティ** ダイアログ ボックスで、 **WCF 拡張機能** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[インポート]**|WCF カスタム動作拡張機能が登録されている WCF 構成ファイルをインポートします。 このボタンをクリックすると開きます、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。 有効な WCF 構成ファイルを選択する必要があります。 WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)です。|  
    |**[エクスポート]**|WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。 このボタンをクリックすると開きます、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。|  
    |**Clear**|既存の WCF カスタム動作拡張機能をアダプター ハンドラーのプロパティから消去します。|  
  
## <a name="see-also"></a>参照  
 [Wcf-customisolated アダプタを構成します。](../core/configuring-the-wcf-customisolated-adapter.md)