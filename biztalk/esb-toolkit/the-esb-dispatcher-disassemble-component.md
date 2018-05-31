---
title: 逆アセンブル コンポーネントの ESB ディスパッチャー |Microsoft ドキュメント
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
ms.openlocfilehash: c846ca716aef72d43e4f4a6ed75a2b20a81c351a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294690"
---
# <a name="the-esb-dispatcher-disassemble-component"></a>ESB ディスパッチャーに逆アセンブル コンポーネント
ESB ディスパッチャーの逆アセンブル コンポーネントは、ディスパッチャーのコンポーネントに同様の方法で送信メッセージのエンドポイントの場所のプロパティを動的に設定できます。 このパイプライン コンポーネントは、Microsoft BizTalk メッセージのバッチ解除機能 (XML 逆アセンブラー クラスから継承することで、名前付き**XmlDasmComp**) ESB 行程を実行できるメカニズムをディスパッチ メッセージBizTalk パイプラインのメッセージング サービスです。