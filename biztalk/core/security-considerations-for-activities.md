---
title: アクティビティのセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bca070662feb0731abb5adbf2147a2e24b5a6e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974115"
---
# <a name="security-considerations-for-activities"></a>アクティビティのセキュリティに関する考慮事項
WCF アダプタの通信データを受信するときに使用するセキュリティ ロールは、他の BAM ソリューションで使用するものと同じです。 このため、WCF アダプタの通信データを受信するときは、使用するユーザーとライタ ロールの適切な選択にも注意を払う必要があります。  
  
 WCF サービスおよび WCF アダプタの使用時には、すべての BAM 関連データが、選択したロールによって BAM プライマリ インポート データベースに書き込まれます。  
  
 適切なユーザー ロール構成の選択基準は、ソリューションのシナリオによって異なります。  
  
- 多くの新しいサービスをさまざまなアクティビティによって追跡し、すべてのサービスを同じユーザー アカウントで実行する必要がある場合は、BAM_EVENT_WRITER スーパー ロールを使用して受信したイベントの書き込みを行うと便利です。  
  
  > [!NOTE]
  >  この場合、ユーザーを BAM イベント ライタ スーパー ロールに追加する必要があります。 ユーザーをスーパー ロールに追加すると、そのユーザーがシステム内のすべてのアクティビティに書き込みを行うことができるようになるため、注意が必要です。  
  
- 書き込み対象のイベントをより厳密に管理する必要がある場合は、アクティビティ固有のロールを使用する必要があります。  
  
  > [!NOTE]
  >  この場合、ユーザーを各アクティビティに固有のイベント ライタ ロールに追加する必要があります。  
  
  BAM イベント ライター ロールを構成する方法の詳細については、次を参照してください。[かを確認し、アクティビティ イベント ライター ロールを設定する方法](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)します。  
  
> [!IMPORTANT]
>  BizTalk Application Users グループのメンバーがあります。  
  
 IIS 使用時の偽装対策のために BAM WCF インターセプタを構成する場合に使用するユーザー アカウントを選択するときは、次のシナリオに基づいて判断する必要があります。  
  
- 自己ホスト型: コンピューターでの実行を実行可能ファイルを保持する WCF サービス開く。  
  
- WCF アダプター: を使用して作成したソリューション、 **Biztalk WCF サービス公開ウィザード**します。  
  
- IIS でホストされる: WCF サービスを使用して、IIS アプリケーションでホストされるソリューションです。  
  
  次の表を基準に、使用するアカウントを決定してください。  
  
|ソリューションの種類|使用するアカウント|  
|-------------------|--------------------|  
|自己ホスト型|サービスをオープンな状態で格納する実行可能ファイルの実行に使用するアカウント。|  
|WCF アダプター|AppPool id を使用します。 これは、受信場所が存在する Vroot に関連付けられた AppPool です。 使用する場合、この id が自動的に作成、 **BizTalk WCF サービス公開ウィザード**サイトを発行します。 これは、IIS ホスト型ソリューションの特殊なケースと考えることができます。|  
|IIS ホスト型|WCF サービスの VRoot/Application を実行する AppPool ユーザーの ID。|  
  
## <a name="see-also"></a>参照  
 [BAM インターセプターのセキュリティに関する考慮事項](../core/security-considerations-for-bam-interceptors.md)