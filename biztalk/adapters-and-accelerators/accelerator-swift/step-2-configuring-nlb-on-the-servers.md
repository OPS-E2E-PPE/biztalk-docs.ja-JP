---
title: 手順 2:サーバーに NLB を構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- configuring, NLB
- NLB
ms.assetid: 30b2f645-b495-49a5-852b-cf89d25fd2b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad409c9a4287cee985d0a7f270370b97d5d8cf4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530013"
---
# <a name="step-2-configuring-nlb-on-the-servers"></a>手順 2:サーバーに NLB を構成します。
基本プラットフォームをインストールして適切なネットワークの設定でサーバーを構成した後 (を参照してください[手順 1。基本プラットフォームのインストール](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md))、BizTalk HTTP フロント エンド サーバーと BizTalk メッセージング サーバーでの負荷分散を有効にする必要があります。 この手順は、1 つまたは複数 BizTalk HTTP フロント エンド サーバーがある 1 つまたは複数の BizTalk メッセージング サーバーから別のコンピューターにインストールされている場合にのみ必要です。  
  
 負荷分散により、高可用性の通信、クライアント コンピューター (Internet Explorer のユーザーが MRSR サイトを参照) と、MRSR サーバー間および MRSR サーバーと、メッセージング サーバーです。  
  
 負荷分散、**パブリック**イントラネット ユーザーは、これらのコンピューター上の IIS Web サーバーに接続を有効に HTTP フロント エンド サーバーのインターフェイスが必要です。 負荷分散、**プライベート**これらのコンピューター上の web サービスにお問い合わせくださいメッセージング サーバーを有効に HTTP フロント エンド サーバーのインターフェイスが必要です。  
  
 メッセージング サーバーに 2 つのサーバーがあると仮定すると構成の負荷分散、**プライベート**ネットワーク アダプター。  
  
 詳細については、BizTalk Server の展開ガイドを参照してください。