---
title: 送信ポートの関連付け (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8624d4c-cee8-4072-bff7-2468d83a06de
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00240fb0214d2c73cbe49920143399b5ca79c327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355292"
---
# <a name="configuring-send-port-association-as2"></a>送信ポートの関連付けの構成 (AS2)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信 AS2 メッセージのアグリーメントを解決するのには、ポートの関連付けを送信します。 AS2 メッセージは、アグリーメントに関連付けられている送信ポートとメッセージをサブスクライブした送信ポートを照合してアグリーメントに解決されます。 このトピックでは、アグリーメントに送信ポートに関連付ける方法の手順を示します。  
  
> [!IMPORTANT]
>  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。 ただし、BizTalk Server 2009 で送信ポートが関連付けられているパーティ レベルで。 旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[構成の全般的なパーティ プロパティ (AS2)](../core/configuring-general-party-properties-as2.md))。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。  
  
> [!IMPORTANT]
>  オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときにアグリーメント。  
>   
>  グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向アグリーメント タブでのみ無効になります。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A について、グリッドが無効になりますで、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-send-port-association"></a>送信ポートの関連付けを構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、次のようにクリックします。**送信ポート**します。  
  
3.  空のセルをクリックして、**名前**列で、ドロップダウン リストから、アグリーメントと関連付ける送信ポートを選択します。 **URI**列には、送信ポートのアドレスが表示されます。  
  
4.  送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**します。  
  
5.  送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメントのプロパティの構成](../core/configuring-as2-agreement-properties.md)