---
title: BizTalk Server を実行しているコンピューターの災害復旧 |Microsoft ドキュメント
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
ms.openlocfilehash: b0ca86ef9a412514fdf3f30f0a38cbac710e0f59
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005227"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a>BizTalk Server を実行しているコンピューターの災害復旧
組織内の BizTalk Server を実行しているコンピューターで、復旧不可能なハードウェア障害が発生した場合、同等のコンピューターに置き換える必要があります。 これは、BizTalk Server データベースは破損しておらず、障害は BizTalk Server を実行しているコンピューターのいずれかで発生したことを前提としています。  
  
 このような場合の災害復旧の方法の 1 つは、環境内の BizTalk Server を実行しているすべてのコンピューターの更新されたイメージを保持しておくことです。 イメージを保存しておけば、コンピューターにハードウェア障害が発生したとき、復旧操作は保存されているイメージを新しいコンピューターに展開するのと同様に簡単です。 ディザスター リカバリーのトピックでは、そのようなイメージを保存しておくことができない場合について説明します。  
## <a name="recovering-different-editions-of-biztalk-server"></a>さまざまなエディションの BizTalk Server の復旧  
 復旧方法は、コンピューターで実行している BizTalk Server のエディションによって異なります。  
  
 BizTalk Server Developer Edition および BizTalk Server Enterprise Edition を実行している複数のコンピューターの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が許可されます。 BizTalk Server を実行しているコンピューターのいずれかで障害が発生した場合、代替コンピューターを用意して、そのコンピューターを既存の BizTalk グループに参加させることができます。 この場合、BizTalk グループに参加させるコンピューターの名前は、障害が発生したコンピューターと同じ名前でも別の名前でもかまいません。  
  
 上記の方法が適していないための BizTalk Server の Standard Edition では、コンピューターを BizTalk グループに参加できません。 代わりに、代替コンピューターとして機能させる新しいコンピューターをセットアップして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成設定を復元します。この操作に必要な手順の概要を以下に示します。 詳細については、次を参照してください。 [BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)です。  
  
## <a name="recovery-phases"></a>復旧フェーズ  
 BizTalk Server を実行しているコンピューターの復旧は、次の 3 つのフェーズに分類できます。  
  
1.  **基本プラットフォームの準備**  
  
     このフェーズでは、オペレーティング システムなどの基本プラットフォーム、必要なソフトウェア、および適切な BizTalk Server コンポーネントが備わったコンピューターを準備します。 このガイドでは、基本プラットフォーム、必要なソフトウェア、および BizTalk Server コンポーネントがインストールされているコンピューターを用意してから、BizTalk Server 構成の復元を試みることを前提としています。 基本プラットフォームの復元については説明しません。  
  
2.  **BizTalk Server の構成を復元します。**  
  
     このフェーズでは、障害が発生したコンピューターの BizTalk Server 構成ファイルのコピーなど、そのコンピューターで構成されていた機能を記録していることを前提としています。 このガイドでは、BizTalk Server 構成を復元する場合に役立つ情報を紹介します。  
  
3.  **BizTalk アプリケーションの復元**  
  
     このフェーズでは、代替コンピューターの BizTalk Server プロセスによってホストされるアプリケーションに関連付けられた、.NET アセンブリを復元します。 ユーザー アセンブリなど、BizTalk アセンブリとは別の必要アイテムを、コンピューターの各場所またはグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。 このガイドでは、このフェーズの一部の手順について説明します。 ただし、BizTalk アプリケーションを復元するための個別のスクリプトやツールは提供していません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のバックアップと復元](../core/backing-up-and-restoring-biztalk-server.md)