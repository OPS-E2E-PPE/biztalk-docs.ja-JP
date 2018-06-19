---
title: 新しいマスター シークレット サーバーを手動で指定する |Microsoft ドキュメント
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
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299802"
---
# <a name="designating-a-new-master-secret-server-manually"></a>新しいマスター シークレット サーバーを手動で指定します。
クラスターのハードウェアは高価にすることはできます。 ハードウェアのコストに問題がある場合は、障害のシナリオの中にマスター シークレット サーバーに別のエンタープライズ シングル サインオン (SSO) サーバーを手動で指定するを検討することができます。 このオプションを使用して、SSO グループの他の SSO サーバーは、マスタ シークレット サーバーに昇格できます。 マスターが下にある場合は、マスター シークレット サーバーを使用する SSO サーバーのいずれかを手動で昇格できます。 この手法の最大の欠点は、既存の展開を編集、既存を再起動できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services、または新しいマスター シークレット サーバーを昇格するまでに、新しい BizTalk アプリケーションを展開します。  
  
 プロセスをシームレスにするには、いくつかの監視メカニズムを実装するため、できるだけ早く障害は検出する必要があります。 System Center Operations Manager などの監視アプリケーションを使用して、昇格プロセスを自動化することもできます。  
  
 マスター シークレット サーバーを手動で移動の詳細については、次を参照してください。[マスター シークレット サーバーを移動する方法](http://go.microsoft.com/fwlink/?LinkId=156841)(http://go.microsoft.com/fwlink/?LinkId=156841) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)