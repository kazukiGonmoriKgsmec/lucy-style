flowchart BT

%% ===== Outcome =====
subgraph Outcome
  B[継続的な月30万円の中小企業診断士収入]
  A[45歳迄に倒産防止共済で800万貯める]
  B --> A
end

%% ===== Output =====
subgraph Output

  %% 顧問契約ルート
  subgraph 顧問ファネル
    C[顧問契約年3件]
    F[年15件の問い合わせ] -->|20%| C
    G[750件の有効リード継続] -->|2%| F
    H[年間250リード追加] -->|保持3年| G
    I[小説読了リード100件] --> H
    J[名刺交換リード100件] --> H
    K[セミナー参加者リード50件] --> H
  end

  %% スポット契約ルート
  subgraph スポットファネル
    D[スポット契約年4件]
    SpotOppty[年20件の問い合わせ] -->|20%| D
    SpotActiveLead[1000件の有効活用] -->|2%| SpotOppty
    SpotLeadGen[年333件の活用者] -->|保持3年| SpotActiveLead
    QiitaContributions[年333貢献者] --> SpotLeadGen
  end

  %% 新規事業ルート
  subgraph 新規事業ファネル
    E[新規事業1件の進行]
    NewBusinessKPI[7年で336件の事業案] -->|0.3%| E
    NewBusinessYearKPI[年48件の事業案] --> NewBusinessKPI
  end

end

%% ===== cross‑subgraph links =====
C --> B
D --> B
E --> B

%% ===== Process =====
subgraph Process

  %% 顧問KPI行動
  subgraph 顧問KPI行動
    L[小説投稿月2本] -->|1話で4人| I
    M[新しい場へ月2回] -->|1回で4人| J
    N[登壇月1回] -->|1回で4人| K
  end

  %% スポットKPI行動
  subgraph スポットKPI行動
    QiitaPostAction[Qiitaに月7本投稿] -->|1本で4人記憶| QiitaContributions
  end

  %% 新規事業KPI行動
  subgraph 新規事業KPI行動
    NewBusinessMonthKPI[月4件のお墓投稿] --> NewBusinessYearKPI
  end

end
