---
title: Wcf-custom 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0208a7aa-6e42-43b7-a934-27ef4409b4ec
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a24977805f9d55ec95784a81a2a2c914d887f440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342265"
---
# <a name="how-to-configure-a-wcf-custom-receive-handler"></a>WCF-Custom 受信ハンドラーを構成する方法
する場合は、受信ハンドラのプロパティを構成する必要があります、 [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] machine.config 以外の場所からカスタム動作拡張機能を検索します。  
  
## <a name="why-should-wcf-custom-adapter-lookup-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>なぜ machine.config 以外の場所から WCF カスタム アダプター参照カスタム動作拡張機能を必要がありますか。  
 使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。動作拡張機能を読み込む前に、 [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] machine.config で動作拡張機能を検索します。ただし、machine.config は、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用が理想的です。 WCF カスタム動作拡張機能でのみ必要とその一方で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターで実行されているすべてのアプリケーションではなく、します。 したがって、machine.config にカスタム動作拡張機能を格納する役目を果たします、中には最適な場所ではありません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アダプター ハンドラーのプロパティは、元の追加の場所を指定、[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]カスタム動作拡張機能を調べることができます。 Machine.config で既に利用できる動作拡張機能は置き換えられませんことに注意してください。  
  
### <a name="additional-considerations"></a>その他の注意点  
 受信ハンドラのプロパティを維持する Wcf-custom を構成するときに、次の点に注意してください。  
  
-   カスタム動作拡張機能は、machine.config かアダプター ハンドラーのプロパティである必要があります。 カスタム動作拡張機能は、両方の場所に重複していない必要があります。  
  
-   カスタム動作拡張機能は、machine.config で利用可能な既にアダプター ハンドラーのプロパティの同じ動作拡張機能を設定しようとする場合は、プロパティを設定しようとするとすぐにエラーを取得します。  
  
-   カスタム動作拡張機能は既にアダプター ハンドラーのプロパティを設定し、同じ動作拡張機能で、machine.config を更新する場合は、ランタイム エラーが発生してもイベント ログに記録されます。 受信場所も無効になります。  
  
-   カスタム動作拡張機能で参照されるアセンブリは、アダプター ハンドラーのプロパティを設定する前に、グローバル アセンブリ キャッシュ (GAC) に存在することがあります。  
  
## <a name="configuring-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティを構成します。  
 受信ハンドラーを Wcf-custom を構成するには、このトピックの手順を使用します。  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティを構成するには  
  
1. BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。  
  
2. 展開したアダプターの一覧でクリックして**Wcf-custom**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**プロパティ**します。  
  
4. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの 、 **WCF 拡張機能** タブで、次の操作を行います。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[インポート]**|WCF カスタム動作拡張機能を持つ WCF 構成ファイルをインポートします。 このボタンをクリックすると、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。 ファイルは有効な WCF 構成ファイルである必要がありますに注意してください。 WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [ http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)します。|  
   |**[エクスポート]**|WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。 このボタンをクリックすると、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。|  
   |**Clear**|アダプター ハンドラーのプロパティから既存の WCF カスタム動作拡張機能をクリアします。|  
  
## <a name="see-also"></a>参照  
 [WCF-Custom アダプターの構成](../core/configuring-the-wcf-custom-adapter.md)