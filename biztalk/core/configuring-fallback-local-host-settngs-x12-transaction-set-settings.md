---
title: フォールバック ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 9fa9e1fcc8bf1764a16142d38058e14878341fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233394"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a>フォールバック ローカル ホスト設定の構成 (X12 トランザクションセットの設定)
受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。 この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。 フォールバック アグリーメントに関するこのページで、フォールバック ターゲットの名前空間を指定します。 どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマについては、「を決定[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。  
  
> [!NOTE]
>  このトピックは、HIPAA 関連の設定にも当てはまります。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>トランザクション セットのローカル ホスト設定を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。  
  
2.  **X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホストの設定**.  
  
3.  選択**暗黙的な 10 進形式 Nn を底 10 の数値を変換**に BizTalk Server での中間 XML で底 10 の数値に形式 Nn で指定された EDI 番号を変換します。  
  
    > [!NOTE]
    >  この変換の後、中間 XML は長さの検証でエラーになる可能性があります。 これは、底 10 の数値形式の番号に 10 進数が含まれるために発生するもので、その番号の長さは Nn 形式の番号より 1 だけ大きくなります。 この問題を解決するにはの値を追加して**1**最小値/最大長の値にします。  
  
4.  選択**末尾の区切り記号に空の XML タグを作成して**末尾の区切り記号に空の XML タグを含めるインターチェンジの送信者にします。  
  
5.  **Target Namespace**、入力 (またはドロップダウン リストから選択) ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して受信メッセージを処理するスキーマを決定します。  
  
6.  をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [設定の X12 フォールバック アグリーメントのプロパティをトランザクション セットの設定](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)