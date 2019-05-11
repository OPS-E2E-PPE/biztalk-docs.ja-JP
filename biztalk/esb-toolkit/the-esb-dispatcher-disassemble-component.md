---
title: ESB ディスパッチャー逆アセンブル コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1f5e46b-8f41-47f8-b22b-b9e9eaac6475
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea0aadf4207d8486e7a7d55c878f7de99efb831
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399830"
---
# <a name="the-esb-dispatcher-disassemble-component"></a>ESB ディスパッチャー逆アセンブル コンポーネント
ESB ディスパッチャー逆アセンブル コンポーネントは、ディスパッチャー コンポーネントと同様の方法で、送信メッセージのエンドポイントの場所のプロパティを動的に設定できます。 このパイプライン コンポーネントは、Microsoft BizTalk メッセージのバッチ解除の機能 (XML 逆アセンブラーのクラスから継承することで、名前付き**XmlDasmComp**) ESB 行程を実行できるメカニズムをディスパッチ メッセージBizTalk パイプラインのメッセージング サービスです。