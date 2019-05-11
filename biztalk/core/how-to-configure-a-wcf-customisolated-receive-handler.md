---
title: Wcf-customisolated 受信ハンドラーを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: dca28fe7ca685f470702cb34ba01f98840692101
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342250"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a>WCF-CustomIsolated 受信ハンドラーを構成する方法
Wcf-customisolated アダプターは、machine.config 以外の場所からカスタム動作拡張機能を参照する場合は、受信ハンドラのプロパティを構成する必要があります。  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a>理由: Wcf-customisolated アダプターを検索する machine.config 以外の場所からカスタム動作拡張機能ですか?  
 使用されるカスタム動作拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]machine.config に登録されます。動作拡張機能を読み込む前に、Wcf-customisolated アダプターは、machine.config で動作拡張機能を検索します。ただし、machine.config は、特定のコンピューターで実行されているすべてのアプリケーションに必要な構成情報を格納する使用が理想的です。 WCF カスタム動作拡張機能でのみ必要とその一方で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターで実行されているすべてのアプリケーションではなく、します。 したがって、machine.config にカスタム動作拡張機能を格納する役目を果たします、中には最適な場所ではありません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アダプター ハンドラーのプロパティは、元の WCF CustomIsolated アダプターがカスタム動作拡張機能を検索できます、追加の場所を指定します。 Machine.config で既に利用できる動作拡張機能は置き換えられませんことに注意してください。  
  
### <a name="additional-considerations"></a>その他の注意点  
 受信ハンドラのプロパティの保持、Wcf-customisolated を構成するときに、次の点に注意してください。  
  
-   カスタム動作拡張機能は、machine.config かアダプター ハンドラーのプロパティである必要があります。 カスタム動作拡張機能は、両方の場所に重複していない必要があります。  
  
-   カスタム動作拡張機能は、machine.config で利用可能な既にアダプター ハンドラーのプロパティの同じ動作拡張機能を設定しようとする場合は、プロパティを設定しようとするとすぐにエラーを取得します。  
  
-   カスタム動作拡張機能は既にアダプター ハンドラーのプロパティを設定し、同じ動作拡張機能で、machine.config を更新する場合は、ランタイム エラーが発生してもイベント ログに記録されます。 受信場所も無効になります。  
  
-   カスタム動作拡張機能で参照されるアセンブリは、アダプター ハンドラーのプロパティを設定する前に、グローバル アセンブリ キャッシュ (GAC) に存在することがあります。  
  
## <a name="configuring-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティを構成します。  
 受信ハンドラーを WCF CustomIsolated を構成するのには、次の手順を使用します。  
  
#### <a name="to-configure-the-adapter-handler-properties"></a>アダプター ハンドラーのプロパティを構成するには  
  
1. BizTalk 管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**を展開し**アダプター**します。  
  
2. 展開したアダプターの一覧でクリックして**Wcf-customisolated**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられている場合、あるホストを選択し、クリックして**プロパティ**します。  
  
4. **Wcf-customisolated トランスポートのプロパティ** ダイアログ ボックスの 、 **WCF 拡張機能** タブで、次の操作を行います。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**[インポート]**|WCF カスタム動作拡張機能を持つ WCF 構成ファイルをインポートします。 このボタンをクリックすると、 **WCF 構成のインポート** ダイアログ ボックスを参照して、WCF 構成ファイルを検索します。 ファイルは有効な WCF 構成ファイルである必要がありますに注意してください。 WCF 構成スキーマの詳細についてを参照してください「Windows Communication Foundation 構成スキーマ」 [ http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)します。|  
   |**[エクスポート]**|WCF カスタム動作拡張機能を WCF 構成ファイルにエクスポートします。 このボタンをクリックすると、 **WCF 構成のエクスポート** ダイアログ ボックスを参照して、WCF 構成ファイルを保存します。|  
   |**Clear**|アダプター ハンドラーのプロパティから既存の WCF カスタム動作拡張機能をクリアします。|  
  
## <a name="see-also"></a>参照  
 [WCF-CustomIsolated アダプターの構成](../core/configuring-the-wcf-customisolated-adapter.md)