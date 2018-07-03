---
title: フォールバック ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb13da3e0bc9e0c3ee676a8bf01d484a4201a80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979027"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>フォールバック ローカル ホスト設定の構成 (X12 トランザクションセットの設定)
受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。 この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。 フォールバック アグリーメントに関するこのページで、フォールバック ターゲットの名前空間を指定します。 どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]決定スキーマについては、「[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
> [!NOTE]
>  このトピックは、HIPAA 関連の設定にも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。  
  
2. **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホストの設定**.  
  
3. 選択**変換には 10 進形式 Nn を底 10 の数値が含まれる**を BizTalk Server での中間 XML で底 10 の数値形式 Nn で指定されている EDI 番号を変換します。  
  
   > [!NOTE]
   >  この変換の後、中間 XML は長さの検証でエラーになる可能性があります。 これは、底 10 の数値形式の番号に 10 進数が含まれるために発生するもので、その番号の長さは Nn 形式の番号より 1 だけ大きくなります。 値を追加することで、この問題を解決できます**1**最小値/最大長の値にします。  
  
4. 選択**末尾の区切り記号に空の XML タグを作成する**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。  
  
5. **Target Namespace**、入力 (またはドロップダウン リストから選択します)、ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、受信メッセージを処理するスキーマを決定します。  
  
6. をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定の X12 フォールバック アグリーメント プロパティの構成](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)