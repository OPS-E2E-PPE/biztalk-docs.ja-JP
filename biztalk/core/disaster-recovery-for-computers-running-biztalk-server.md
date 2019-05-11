---
title: BizTalk Server を実行しているコンピューターのディザスター リカバリー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7469c97409ce53a995db95b263f5874e737a9905
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350994"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a>BizTalk Server を実行しているコンピューターのディザスター リカバリー
組織内の BizTalk Server を実行しているコンピューターに、回復不可能なハードウェア障害が低下した場合は、同一のコンピューターで置き換える必要があります。 これは、すべての BizTalk Server データベースが破損しておらず、および BizTalk Server を実行しているコンピューターのいずれかでは、障害であると仮定します。  
  
 方法の 1 つのインストールで BizTalk Server を実行しているすべてのコンピューターの更新されたイメージを維持することです。 コンピューターがハードウェア障害が低下したときに復旧アクションは、保存されたイメージを新しいコンピューターに展開するだけです。 障害復旧に関するトピックでこのようなイメージを格納することは不可能場合について説明します。  
## <a name="recovering-different-editions-of-biztalk-server"></a>BizTalk Server のさまざまなエディションを回復します。  
 復旧方法は、コンピューターで実行されている BizTalk Server のエディションによって異なります。  
  
 BizTalk Server Developer Edition および BizTalk Server Enterprise Edition を実行している複数のコンピューターの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が許可されます。 BizTalk Server を実行しているコンピューターのいずれかが失敗した場合、代替コンピューターを準備し、既存の BizTalk グループに参加できます。 この場合、同じ名前または別の名前を使用しているコンピューターを BizTalk グループに参加できます。  
  
 BizTalk Server の Standard Edition では、上記の方法が適していないために、BizTalk グループにコンピューターを結合できません。 代わりに、新しいコンピューターを設定し、復元に必要な手順を説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]その代替として機能させるための構成設定。 詳細については、次を参照してください。 [BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)します。  
  
## <a name="recovery-phases"></a>復旧フェーズ  
 BizTalk Server を実行しているコンピューターの回復は、3 つのフェーズを以下に分類できます。  
  
1.  **基本プラットフォームの準備**  
  
     このフェーズには、オペレーティング システム、ソフトウェアの前提条件および適切な BizTalk Server コンポーネントを含むベースのプラットフォームで、コンピューターの準備が含まれています。 このガイドでは、BizTalk Server の構成を復元しようとすると、前に、基本プラットフォーム、前提条件、および BizTalk Server コンポーネントがインストールされているコンピューターがあることを前提としています。 このガイドでは、基本プラットフォームの復元は含まれません。  
  
2.  **BizTalk Server 構成を復元します。**  
  
     このフェーズでは、そのコンピューターの BizTalk Server 構成ファイルのコピーを含む、失敗したコンピューターで構成されている機能のレコードがあることを前提としています。 このガイドでは、BizTalk Server の構成を復元するためのガイダンスを提供します。  
  
3.  **BizTalk アプリケーションの復元**  
  
     このフェーズでは、代替コンピューター上の BizTalk Server プロセスによってホストされているアプリケーションで接続されている .NET アセンブリを復元する必要があります。 それぞれの場所またはコンピューターのグローバル アセンブリ キャッシュ (GAC) に、BizTalk アセンブリとは別のユーザー アセンブリなど、必要なすべてのアイテムをインストールする必要があります。 このガイドでは、このフェーズでいくつかのガイダンスを提供します。 ただし、ない個別のスクリプトや BizTalk アプリケーションを復元するためのツール。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のバックアップと復元](../core/backing-up-and-restoring-biztalk-server.md)