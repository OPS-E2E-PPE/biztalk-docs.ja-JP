---
title: 新しいマスター シークレット サーバーを手動で指定する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e198d5aa82b22170fe4ed52115bf7c72b0c55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305785"
---
# <a name="designating-a-new-master-secret-server-manually"></a>新しいマスター シークレット サーバーを手動で指定します。
クラスターのハードウェアは高価にすることはできます。 ハードウェアのコストが重要である場合は、障害のシナリオの中にマスター シークレット サーバーに別のエンタープライズ シングル サインオン (SSO) サーバーを手動で指定することを検討できます。 このオプションを使用して、SSO グループの他の SSO サーバーは、マスター シークレット サーバーに昇格できます。 マスターは、ときに、マスター シークレット サーバーを使用する SSO サーバーのいずれかを手動で昇格できます。 この手法の最大の欠点は、既存の展開を編集、既存を再起動できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス、または新しいマスター シークレット サーバーを昇格するまで、新しい BizTalk アプリケーションをデプロイします。  
  
 プロセスをシームレスにするは、エラーをできるだけ早く検出ができるように、いくつかの監視メカニズムを実装する必要があります。 System Center Operations Manager などの監視アプリケーションを使用して、昇格プロセスを自動化することもできます。  
  
 マスター シークレット サーバーを手動で移動する方法についての詳細については、次を参照してください。[マスター シークレット サーバーを移動する方法](http://go.microsoft.com/fwlink/?LinkId=156841)(<http://go.microsoft.com/fwlink/?LinkId=156841>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバーのクラスタリング](../technical-guides/clustering-the-master-secret-server.md)