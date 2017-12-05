---
title: "パーティの全般プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbabf7e5-6388-4900-ad47-cf5d5af396b5
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6816a432b7a1c1ba5163d922cd1754ebcb398389
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-general-party-properties"></a>パーティの全般プロパティの構成
パーティまたは取引先は、ビジネス リレーションシップの参加組織を表します。 パーティのプロパティには次の情報が含まれます。  
  
-   パーティ名などの全般情報  
  
-   パーティに関連付けられた送信ポート  
  
-   パーティに関連付けられた証明書  
  
 パーティまたは取引先の詳細については、次を参照してください。[取引パートナー](../core/trading-partners-and-business-profiles.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-party-properties"></a>パーティのプロパティを設定するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  **全般**のページ、**パーティ プロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|パーティ名を入力します。|  
    |**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理します。**|パーティが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をホストしている同じ取引先を表すように指定する場合は、このチェック ボックスをオンにします。 **重要:**に付属する既定のパイプラインを使用するソリューション 2 パーティ TPM の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、少なくとも 1 つのパーティの場合は、このチェック ボックスを選択する必要があります。 **注:**このチェック ボックスをオフにすると、一部のプロパティは、このパーティのアグリーメントの作成中に無効になります。|  
    |**追加のプロパティ – 名前/値**|パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。 名前と値の組み合わせは、必要な数だけ追加できます。 **注:**なんらかの処理の名前と値のペアが、BizTalk Server によって使用されません。 このデータは、情報提供のみを目的のはします。|  
    |**Del**|選択した名前と値の組み合わせを削除する場合にクリックします。|  
  
3.  **送信ポート**のページ、**パーティ プロパティ** ダイアログ ボックスで、次の操作です。  
  
    > [!NOTE]
    >  BizTalk Server では、送信ポートの関連付けはアグリーメント レベルで行われます。 **送信ポート**下位互換性は、パーティのプロパティの一部として使用可能なページです。 送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。 ただし、その逆は真ではありません。 送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。 送信ポートをアグリーメントに関連付ける方法の詳細については、次を参照してください。[を構成する送信ポートの関連付け (X12)](../core/configuring-send-port-association-x12.md)または[送信ポート (EDIFACT) の関連付けを構成する](../core/configuring-send-port-association-edifact.md)です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**送信ポートの名前**|ドロップダウン リストから、このパーティにバインドする送信ポートを選択します。|  
    |**送信ポートの URI**|送信ポートのアドレスを表示します。|  
    |**[削除]**|選択した送信ポートをパーティから削除する をクリックします。|  
    |**プロパティ**|クリックすると表示、**送信ポートのプロパティ**選択した送信ポートのダイアログ ボックス。|  
  
4.  **証明書** ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**参照**|クリックすると表示、**証明書の選択**ダイアログ ボックスで、パーティに送信されるメッセージに適用するローカル コンピューターまたはその他のユーザーの証明書ストアから署名証明書を選択します。|  
    |**共通名**|選択した証明書の説明を表示します。|  
    |**拇印**|パーティの解決および署名の確認に使用される秘密キー証明書の拇印を表示します。 証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。|  
    |**証明書を削除します。**|表示されている証明書を削除する場合にクリックします。|  
  
5.  をクリックして**適用**、プロパティを受け入れるか、をクリックする**[ok]**構成設定を完了します。 どちらの操作では、設定を検証します。  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティの構成](../core/configuring-edi-properties.md)